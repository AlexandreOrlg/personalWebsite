<script>
    import Link from "../Link.svelte";
    import {onMount} from "svelte";
    import {quartInOut} from "svelte/easing";
    import { fly } from 'svelte/transition';


    let ready = false;
    onMount(() => ready = true);
</script>

{#if ready}
<div>
<h2  transition:fly={{ delay: 400, duration: 500 , y: 50, easing: quartInOut }} >Expériences</h2>
<div class="projects-container"  transition:fly={{ delay: 600, duration: 500 , y: 50, easing: quartInOut }}>

    <div>
        <div class="link-container">
            <Link class="link"
                  preview="hellowork.png"
                  description="HelloWork Group est le premier acteur digital français de l’emploi, du recrutement et de la formation. A travers ses différentes solutions, le groupe accompagne les actifs tout au long de leur vie professionnelle, les entreprises, cabinets de recrutement et les centres de formation/écoles sur la valorisation de leurs offres de formation."
                  href="https://hellowork.com"
            > Seekube <span style="font-size: 10px; text-decoration: none">by Hellowork</span></Link>
            <p>2022 → Maintenant</p>
        </div>
        <p>Product Manager</p>
    </div>
    <div>
        <div class="link-container"
        >
            <Link class="link"  preview="seekube.png"
                  description="Seekube est la plateforme leader de forums virtuels de recrutement pour les acteurs de l'emploi et de la formation. Via notre plateforme online de recrutement, nous permettons à tout candidat et toute entreprise/école de se rencontrer et d’échanger indépendamment de leur localisation."
                  href="https://seekube.com">Seekube</Link>
            <p>2021 → 2022</p>
        </div>
        <p>Product Owner / Product Designer </p>
    </div>
    <div>
        <div class="link-container">
            <Link class="link"   preview="blober.png"
                  description="Blober révolutionne la manière dont vous racontez des histoires en ligne. Nous simplifions la création de webstories pour enrichir votre contenu, optimiser la communication et engager votre audience. Pas de codage, pas de tracas, juste un storytelling fluide et efficace pour tous les domaines, du marketing au milieu culturel."
            href="http://blober.app"
            >Blober.app</Link>
            <p>2020 → Maintenant</p>
        </div>
        <p>Co-fondateur - En charge du produit et de la technique</p>
    </div>
    <div>
        <div class="link-container">
            <Link
                    class="link"
                  description="Esprit Libre est une agence de communication et de marketing créatif spécialisée dans le développement de territoires de marque. Forte de plusieurs années d'expérience, l'agence a réussi à établir des partenariats solides avec des institutions publiques telles que la Ville et le Pays de Martigues. Elle a également étendu son influence dans le secteur privé, collaborant avec des marques renommées comme Leroy Merlin, Blédina, Elle&Vire et Valrhona."
            >Esprit Libre</Link>
            <p>2017 → 2020</p>
        </div>
        <p>Responsable des projets digitaux</p>
    </div>
</div>
</div>
{/if}
<style>
    .projects-container {
        display: flex;
        flex-direction: column;
        gap: 16px;
    }

    h2 {
        margin-top: 64px;
        margin-bottom: 24px;
    }

    .link-container {
        display: flex;
    }

    :global(a.link) {
        text-decoration: underline;
        text-underline-offset: 0.3em;
        text-decoration-color: var(---slate-300);
        text-decoration-thickness: 1px;
        font-size: 16px;
        font-weight: 600;
    }

    .link-container p {
        margin-left: 6px;
        color: var(--slate-500);
    }

    p {
        margin-top: 2px;
        color: var(---slate-500);
        font-size: 14px;
        font-weight: 400;
        margin-left: 4px;
        line-height: 130%;
    }

    .link-container  p {
        margin-top: 5px;
    }
</style>