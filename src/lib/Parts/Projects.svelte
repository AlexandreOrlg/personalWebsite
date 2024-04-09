<script>
    import Link from "../Link.svelte";
    import ArrowUpRight from "lucide-svelte/dist/svelte/icons/arrow-up-right.svelte"
    import {onMount} from "svelte";
    import {quartInOut} from "svelte/easing";
    import { fly } from 'svelte/transition';


    let ready = false;
    onMount(() => ready = true);

</script>
{#if ready}
<div>
<h2 transition:fly={{ delay: 400, duration: 500 , y: 50, easing: quartInOut }} >Projets</h2>

    <div class="projects-container" transition:fly={{ delay: 600, duration: 500 , y: 50, easing: quartInOut }}>
        <div>
            <div class="link-container">
                <Link class="link" preview="iasterisk.png" description="Iasterisk est le premier correcteur conçu pour ceux qui souhaitent rester discrets lorsqu'ils corrigent leur texte, alimenté par GPT d'OpenAI. Son fonctionnement est très simple : il récupère le texte de votre presse-papiers, le corrige, et remplace votre presse-papiers par le texte corrigé." href="https://github.com/AlexandreOrlg/Iasterisk">Iasterisk</Link>
            </div>
            <p>Un correcteur orthographique propulsé par l'IA.</p>
        </div>
    <div>
        <div class="link-container">
            <Link class="link"
            preview="sveltecmd.png"
                  description="SvelteCmd est un ensemble de composants pour créer la palette de commandes idéale pour votre application web. Conçu pour être universellement accessible, extrêmement flexible et personnalisable."
href="https://alexandreorliaguet.fr/sveltecmd/"
            > SvelteCmd</Link>
        </div>
        <p>Composant de menu de commande simple et sans style en Svelte.</p>
    </div>
    <div>
        <div class="link-container">
            <Link class="link" preview="blober.png"
                  href="http://blober.app"
                  description="Blober révolutionne la manière dont vous racontez des histoires en ligne. Nous simplifions la création de webstories pour enrichir votre contenu, optimiser la communication et engager votre audience. Pas de codage, pas de tracas, juste un storytelling fluide et efficace pour tous les domaines, du marketing au milieu culturel."
            >Blober.app</Link>
        </div>
        <p>Un éditeur de webstories facile à utiliser.</p>
    </div>
    </div>
</div>
{/if}
<style>

    p {
        margin-left: 4px;
    }

    .projects-container{
        display: flex;
        flex-direction: column;
        gap: 16px;
    }

    h2 {
        margin-top: 64px;
        margin-bottom: 24px;
    }

    .link-container{
        display: flex;
    }

    :global(.link-container svg){
        color: var(---slate-500);
    }

    p{
        margin-top: 2px;
        color: var(---slate-500);
        font-size: 14px;
        font-weight: 400;
        margin-left: 4px;
        line-height: 130%;
    }
</style>