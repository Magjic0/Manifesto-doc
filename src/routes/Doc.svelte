<!-- ================= HERO (minimal) ================= -->
<section class="hero" aria-label="Introduction">
    <div class="hero-content">
        <h1 class="headline">Build, ship<br />for the rest&nbsp;of&nbsp;us</h1>
        <a href="/doc/deploy" class="btn-primary">Get&nbsp;Started →</a>
    </div>
</section>

<!-- ================= DICTION ================= -->
<section class="definition">
    <h2><span class="accent">/‵manifɛsto/</span></h2>
    <p class="lead">Manifesto est un écosystème qui rassemble pipeline de déploiement, suite d’apps de productivité et gestion de projet agile afin d’accélérer la livraison logicielle.</p>
</section>

<!-- ================= FEATURES GRID ================= -->
<section class="features-section">
    <div class="features-grid">
        <article>
            <h3>Pipeline de déploiement élégante</h3>
            <p>Automatisation complète : Docker, Traefik, CI/CD. Vous poussez, nous livrons.</p>
        </article>
        <article>
            <h3>Suite d’apps de productivité</h3>
            <p>Chronomètre, notes, tâches… Des outils minimalistes, intégrés et cohérents.</p>
        </article>
        <article>
            <h3>Gestion de projet agile</h3>
            <p>Backlog, sprints, reporting temps réel — SCRUM sans friction pour votre équipe.</p>
        </article>
    </div>
</section>

<!-- ================= CTA ================= -->
<section class="bottom-cta">
    <p>Ready to build something great ?</p>
    <a href="/doc/deploy" class="btn-primary big">Déployer ma première app</a>
</section>

<style>
    :global(body) { margin: 0; }

    /* -------- HERO -------- */
    .hero {
        text-align: center;
        padding: 8rem 1.5rem 6rem;
    }
    @media (min-width: 960px) { .hero { padding: 10rem 3rem 8rem; } }
    .hero-content { max-width: 46rem; margin: 0 auto; }
    .headline { font-size: clamp(2.8rem, 6vw, 5rem); line-height: 1.1; margin: 0 0 2.5rem; font-weight: 700; }

    /* Primary button */
    .btn-primary {
        display: inline-block;
        background: var(--color-theme-2);
        color: #fff;
        padding: 1rem 2.6rem;
        border-radius: 999px;
        font-weight: 600;
        font-size: 1.1rem;
        text-decoration: none;
        transition: background 0.2s, transform 0.15s;
    }
    .btn-primary:hover { background: var(--color-theme-1); transform: translateY(-2px); }

    /* -------- DEFINITION -------- */
    .definition { text-align: center; padding: 6rem 1.5rem 4rem; max-width: 40rem; margin: 0 auto; }
    .accent { color: var(--color-theme-2); font-size: 2.4rem; font-family: serif; }
    .lead { font-size: 1.25rem; line-height: 1.6; }

    /* -------- FEATURES -------- */
    .features-section { padding: 6rem 1.5rem; background: transparent; }
    .features-grid { display: grid; gap: 4rem 2rem; max-width: 70rem; margin: 0 auto; }
    .features-grid h3 { font-size: 1.6rem; margin-bottom: 0.75rem; }
    .features-grid p { font-size: 1.05rem; line-height: 1.6; }
    @media (min-width: 900px) { .features-grid { grid-template-columns: repeat(3, 1fr); } }

    /* -------- BOTTOM CTA -------- */
    .bottom-cta { text-align: center; padding: 6rem 1.5rem 8rem; }
    .bottom-cta p { font-size: 1.8rem; margin: 0 0 2rem; font-weight: 600; }
    .big { margin-top: 1rem; }
</style>

