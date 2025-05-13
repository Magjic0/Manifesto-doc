<script lang="ts">
    export const prerender = true;
</script>

<!-- ░░░ Sommaire — collé en haut, centré ░░░ -->
<nav class="toc" aria-label="Sommaire">
    <a href="#deploy">Déployer</a>
    <a href="#update">Mettre à jour</a>
</nav>

<article class="doc">

    <!-- =========== Bloc DÉPLOYER =========== -->
    <section id="deploy">
        <h1>Déployer une application</h1>

        <div class="steps">
            <article class="step">
                <h2>1. Ajouter le sous‑domaine</h2>
                <p>Dans votre espace <strong>OVH</strong>, créez un enregistrement <code>A</code> pour votre sous‑domaine et faites‑le pointer vers <code>212.83.130.101</code>.</p>
            </article>

            <article class="step">
                <h2>2. Se connecter au serveur</h2>
                <pre><code class="language-bash">ssh root@212.83.130.101
git clone &lt;votre‑repo.git&gt;
cd &lt;votre‑repo&gt;</code></pre>
            </article>

            <article class="step">
                <h2>3. Créer <code>.env</code></h2>
                <pre><code class="language-bash"> nano .env</code></pre>
                <pre><code class="language-env">APP_NAME=nom_de_lapp</code></pre>
                <p class="note">Le nom doit correspondre exactement au dossier de l’application.</p>
            </article>

            <article class="step">
                <h2>4. Lancer les conteneurs</h2>
                <pre><code class="language-bash">docker-compose up -d</code></pre>
            </article>

            <article class="step">
                <h2>5. Régénérer les certificats HTTPS</h2>
                <pre><code class="language-bash">cd ~/traefik
docker-compose -f docker-compose-traefik.yml down
docker-compose -f docker-compose-traefik.yml up -d</code></pre>
            </article>
        </div>
    </section>

    <!-- =========== Bloc UPDATE =========== -->
    <section id="update">
        <h1>Mettre à jour une application</h1>

        <div class="steps">
            <article class="step">
                <h2>1. Se connecter et se placer dans le dossier</h2>
                <pre><code class="language-bash">ssh root@212.83.130.101
cd /var/www/nom_de_lapp</code></pre>
            </article>

            <article class="step">
                <h2>2. Mettre à jour et reconstruire</h2>
                <pre><code class="language-bash">docker-compose down
git pull
docker-compose up -d --build</code></pre>
            </article>
        </div>
    </section>
</article>

<style>
    /* ---------- Sommaire ---------- */
    .toc{
        position:sticky; top:0;
        display:flex; gap:3rem; justify-content:center;
        padding:.75rem 1rem; background:rgba(255,255,255,.85);
        backdrop-filter:blur(6px); border-bottom:1px solid #ddd;
        z-index:20;
    }
    .toc a{
        font-weight:600; text-decoration:none; color:var(--color-text);
        position:relative; padding:.25rem 0;
    }
    .toc a::after{
        content:''; position:absolute; left:0; bottom:-3px;
        width:100%; height:2px; background:var(--color-theme-2);
        transform-origin:left; transform:scaleX(0); transition:transform .2s;
    }
    .toc a:hover,
    .toc a:focus{ color:var(--color-theme-2);}
    .toc a:hover::after{ transform:scaleX(1);}

    /* ---------- Conteneur doc ---------- */
    .doc{ max-width:64rem; margin:0 auto; padding:5rem 1.5rem 8rem; }
    h1{ font-size:clamp(1.9rem,3.5vw,2.6rem); margin:4rem 0 2.5rem; text-align:center; }
    h2{ font-size:1.25rem; margin:0 0 1rem; color:var(--color-theme-2); font-weight:600; }

    /* ---------- Grille des steps ---------- */
    .steps{ display:grid; gap:3rem; }
    .step{
        background:#fff; border-radius:14px;
        box-shadow:0 3px 10px rgb(0 0 0 / 6%);
        padding:2rem 1.75rem; overflow:hidden;
    }
    .note{ margin-top:.75rem; font-size:.9rem; font-style:italic; }

    /* ---------- Code blocks ---------- */
    pre{
        background:var(--color-bg-1); border-radius:8px;
        padding:1rem 1.25rem; font-size:.92rem;
        overflow-x:auto; line-height:1.45;
    }
    code{ font-family:var(--font-mono); }

    /* ---------- Responsive ---------- */
    @media(min-width:900px){
        .steps{ gap:3.5rem; }
    }
    @media(max-width:600px){
        .toc{ gap:1.5rem; padding:.6rem; }
        .step{ padding:1.5rem 1.25rem; }
    }
</style>

