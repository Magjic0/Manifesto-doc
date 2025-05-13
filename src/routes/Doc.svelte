<article class="doc text-column">
    <h1>Déployer une application</h1>

    <!-- Étape 1 -->
    <section class="step">
        <h2>Étape&nbsp;1&nbsp;— Ajouter le sous‑domaine</h2>
        <p>
            Dans votre espace <strong>OVH</strong>, créez un enregistrement
            <code>A</code> pour votre sous‑domaine et faites‑le pointer vers
            <code>212.83.130.101</code>.
        </p>
    </section>

    <!-- Étape 2 -->
    <section class="step">
        <h2>Étape&nbsp;2&nbsp;— Se connecter au serveur</h2>
        <pre><code class="language-bash">ssh root@212.83.130.101</code></pre>
        <p>Puis&nbsp;:</p>
        <pre><code class="language-bash">git clone &lt;votre‑repo.git&gt;
cd &lt;votre‑repo&gt;</code></pre>
    </section>

    <!-- Étape 3 -->
    <section class="step">
        <h2>Étape&nbsp;3&nbsp;— Créer le fichier <code>.env</code></h2>
        <pre><code class="language-bash">touch .env
nano .env</code></pre>
        <pre><code class="language-env">APP_NAME=nom_de_lapp</code></pre>
        <p><em>Le nom doit correspondre exactement au dossier de l’application.</em></p>
    </section>

    <!-- Étape 4 -->
    <section class="step">
        <h2>Étape&nbsp;4&nbsp;— Lancer les conteneurs</h2>
        <pre><code class="language-bash">docker-compose up -d</code></pre>
    </section>

    <!-- Étape 5 -->
    <section class="step">
        <h2>Étape&nbsp;5&nbsp;— Régénérer les certificats&nbsp;HTTPS</h2>
        <pre><code class="language-bash">cd ~/traefik
docker-compose -f docker-compose-traefik.yml down
docker-compose -f docker-compose-traefik.yml up -d</code></pre>
    </section>

    <h1>Mettre à jour une application</h1>

    <!-- Update Étape 1 -->
    <section class="step">
        <h2>Étape&nbsp;1&nbsp;— Se connecter et se placer dans le dossier</h2>
        <pre><code class="language-bash">ssh root@212.83.130.101
cd /var/www/nom_de_lapp</code></pre>
    </section>

    <!-- Update Étape 2 -->
    <section class="step">
        <h2>Étape&nbsp;2&nbsp;— Mettre à jour et reconstruire</h2>
        <pre><code class="language-bash">docker-compose down
git pull
docker-compose up -d --build</code></pre>
    </section>
</article>

<style>
    .doc {
        gap: 2rem;
        padding: 2rem 0;
    }

    .step {
        background-color: rgba(255, 255, 255, 0.45);
        border-radius: 12px;
        box-shadow: 0 2px 8px rgb(0 0 0 / 8%);
        padding: 1.5rem;
        margin-top: 2rem;
    }

    .step h2 {
        margin-top: 0;
        color: var(--color-theme-2);
        font-weight: 600;
    }

    pre {
        background-color: rgba(255, 255, 255, 0.8);
        border-radius: 4px;
        padding: 0.75rem;
        overflow-x: auto;
        font-size: 0.9rem;
    }
</style>