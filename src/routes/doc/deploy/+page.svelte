<div class="doc">

    <!-- =========== Bloc DÉPLOYER =========== -->
    <section id="deploy">
        <h1>Déployer une App</h1>

        <div class="steps">

            <article class="step">
                <h2>Étape 1</h2>
                <p>Sur <strong>OVH</strong>, ajoutez un sous‑domaine en zone DNS de type <code>A</code> pointant vers l'ip
                    <code>***.***.***.***</code></p>
            </article>

            <article class="step">
                <h2>Étape 2</h2>
                <p>Connectez‑vous au serveur :</p>
                <pre><code class="language-bash">ssh root@***.***.***.***</code></pre>
                <p>Faites un <code>git clone</code> de votre dépôt et déplacez‑vous dedans.</p>
            </article>

            <article class="step">
                <h2>Étape 3</h2>
                <p>Créez un fichier <code>.env</code> contenant :</p>
                <pre><code class="language-env">APP_NAME=nom_de_l'app</code></pre>
                <p class="note">Le nom doit correspondre <strong>exactement</strong> au nom du dossier de l’app.</p>
                <p>Commandes à exécuter :</p>
                <pre><code class="language-bash">nano .env</code></pre>
                <p>Puis utilisez les raccourcis : <kbd>Ctrl</kbd>+<kbd>X</kbd>, <kbd>Y</kbd>, <kbd>Entrée</kbd></p>
            </article>

            <article class="step">
                <h2>Étape 4</h2>
                <p>Lancez les conteneurs :</p>
                <pre><code class="language-bash">docker-compose up -d</code></pre>
            </article>

            <article class="step">
                <h2>Étape 5</h2>
                <p>Relancez <code>traefik</code> pour régénérer les certificats HTTPS :</p>
                <pre><code class="language-bash">cd ~/traefik
docker-compose -f docker-compose-traefik.yml down
docker-compose -f docker-compose-traefik.yml up -d</code></pre>
            </article>

            <a href="/doc/update" class="button">Mettre à jour une app →</a>
        </div>
    </section>
</div>

<style>
    .doc {
        max-width: 64rem;
        margin: 0 auto;
        padding: 5rem 1.5rem 8rem;
    }

    h1 {
        font-size: clamp(1.9rem, 3.5vw, 2.6rem);
        margin: 4rem 0 2.5rem;
        text-align: center;
    }

    h2 {
        font-size: 1.25rem;
        margin: 0 0 1rem;
        color: var(--color-theme-2);
        font-weight: 600;
    }

    .steps {
        display: grid;
        gap: 3rem;
    }

    .step {
        background: #fff;
        border-radius: 14px;
        box-shadow: 0 3px 10px rgb(0 0 0 / 6%);
        padding: 2rem 1.75rem;
        overflow: hidden;
    }

    .note {
        margin-top: 0.75rem;
        font-size: 0.9rem;
        font-style: italic;
    }

    pre {
        background: var(--color-bg-1);
        border-radius: 8px;
        padding: 1rem 1.25rem;
        font-size: 0.92rem;
        overflow-x: auto;
        line-height: 1.45;
    }

    kbd {
        background: #eee;
        border-radius: 4px;
        border: 1px solid #ccc;
        padding: 2px 6px;
        font-size: 0.85rem;
        margin-right: 4px;
    }

    .button {
        background: var(--color-theme-2);
        color: #fff;
        width: fit-content;
        padding: 1rem 2.6rem;
        border-radius: 999px;
        margin: 2rem 1rem 0 1rem;
        font-weight: 600;
        font-size: 1.1rem;
        text-decoration: none;
        transition: background 0.2s, transform 0.15s;
    }
    .button:hover { background: var(--color-theme-1); transform: translateY(-2px); }

    @media (min-width: 900px) {
        .steps {
            gap: 3.5rem;
        }
    }

    @media (max-width: 600px) {
        .step {
            padding: 1.5rem 1.25rem;
        }
    }
</style>
