<script>
    import Doc from './Doc.svelte';
    export const prerender = true;
</script>

<svelte:head>
    <title>Documentation — Manifesto</title>
    <meta name="description" content="Guide pour déployer et mettre à jour vos apps Manifesto." />
</svelte:head>

<main class="text-column">
    <Doc />
</main>

<style>
    /* Simple wrapper pour centrer le contenu */
    main {
        padding: 2rem 1rem;
        display: flex;
        justify-content: center;
    }
</style>