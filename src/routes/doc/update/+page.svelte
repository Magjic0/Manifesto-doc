<div class="doc">

    <!-- =========== Bloc MISE À JOUR =========== -->
    <section id="update">
        <h1>Mise à jour d'une App</h1>

        <div class="steps">

            <article class="step">
                <h2>Étape 1</h2>
                <p>Connectez‑vous au serveur :</p>
                <pre><code class="language-bash">ssh root@***.***.***.***</code></pre>
                <p>Et déplacez‑vous dans le dossier de l’application.</p>
            </article>

            <article class="step">
                <h2>Étape 2</h2>
                <p>Coupez Docker, mettez à jour le dépôt, puis relancez avec <code>--build</code> :</p>
                <pre><code class="language-bash">docker-compose down
git pull
docker-compose up -d --build</code></pre>
            </article>

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
