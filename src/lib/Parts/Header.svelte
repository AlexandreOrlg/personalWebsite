<script>
    import UserCircle from 'lucide-svelte/dist/svelte/icons/user-circle-2.svelte'
    import Package from 'lucide-svelte/dist/svelte/icons/package.svelte'
    import Brain from 'lucide-svelte/dist/svelte/icons/brain.svelte'
    import Search from 'lucide-svelte/dist/svelte/icons/search.svelte'
    import Rocket from 'lucide-svelte/dist/svelte/icons/rocket.svelte'
    import PaintBrush from 'lucide-svelte/dist/svelte/icons/paintbrush.svelte'
    import FlaskRound from 'lucide-svelte/dist/svelte/icons/flask-round.svelte'
    import Ruler from 'lucide-svelte/dist/svelte/icons/ruler.svelte'
    import Sparkles from 'lucide-svelte/dist/svelte/icons/sparkles.svelte'
    import BriefCase from 'lucide-svelte/dist/svelte/icons/briefcase.svelte'
    import Link from "$lib/Link.svelte";
    import {fly} from 'svelte/transition';
    import {quartInOut} from 'svelte/easing';
    import {onMount} from 'svelte'

    let ready = false;
    onMount(() => ready = true);
</script>

{#if ready}
    <div class="header">
        <div class="header__title">
            <img src="avatar.png" class="avatar" height="24">
            <div>
                <div style="font-weight: 500; font-size: 20px">Alexandre Orliaguet</div>
                <div class="accent" style="font-size: 16px">Indie maker • Product manager • Product designer
                    <br />

                </div>
            </div>
        </div>

        <div transition:fly={{ delay: 200, duration: 500 , y: 50, easing: quartInOut }}>
            Bienvenue dans mon petit coin d'Internet ! <Rocket strokeWidth="1.6"/>
            <br>
            Passionné par la création de produits
            <Sparkles strokeWidth="1.6"/>
            et l'élaboration d'expériences utilisateur <UserCircle strokeWidth="1.6" /> uniques. Je suis actuellement Product Manager chez

            <Link
                    preview="seekube.png"
                    description="Seekube est la plateforme leader de forums virtuels de recrutement pour les acteurs de l'emploi et de la formation. Via notre plateforme online de recrutement, nous permettons à tout candidat et toute entreprise/école de se rencontrer et d’échanger indépendamment de leur localisation."
                  href="http://seekube.com" target="_blank">
                <svg height="18" viewBox="0 0 14 16" style="margin-right: 4px; margin-bottom: -2px" fill="none"
                     xmlns="http://www.w3.org/2000/svg">
                    <path fill-rule="evenodd" clip-rule="evenodd"
                          d="M0.232894 3.83917L6.56054 0.0982971C6.64465 0.0300473 6.74995 -0.00450988 6.85562 0.000472312C6.95144 0.00307906 7.04498 0.0376378 7.12064 0.0998734L13.4495 3.8415C13.4601 3.84774 13.4703 3.85436 13.4801 3.86133C13.5381 3.89759 13.588 3.94836 13.624 4.01221C13.682 4.11507 13.6933 4.23291 13.6648 4.34146V11.7373C13.6648 11.763 13.6627 11.7882 13.6587 11.8128C13.6534 11.8729 13.6356 11.9324 13.6045 11.9877C13.5639 12.0597 13.5057 12.1151 13.4383 12.1519C13.4112 12.181 13.3796 12.2067 13.344 12.2278L7.0609 15.9423C6.98263 15.9886 6.89565 16.0061 6.81116 15.9981C6.73409 15.9996 6.65567 15.9804 6.58408 15.938L0.317671 12.2334C0.211763 12.2045 0.118053 12.1358 0.0603001 12.0334C0.0309904 11.9814 0.0136723 11.9256 0.00744434 11.869C0.00255606 11.842 0 11.8143 0 11.7859V4.27469C0 4.23132 0.00595866 4.18939 0.0170792 4.14971C0.0219341 4.12578 0.0288418 4.10211 0.0378717 4.07894C0.071729 3.9813 0.138397 3.89504 0.232894 3.83917ZM6.40597 14.7929L1.33071 11.7925L6.40597 8.79201V14.7929ZM0.874538 5.01215L5.97415 8.02702L0.874538 11.0419V5.01215ZM12.7902 10.9962V5.01529L7.73189 8.00573L12.7902 10.9962ZM7.2805 8.75913L12.3588 11.7614L7.2805 14.7636V8.75913ZM6.40639 7.26394L1.30504 4.24808L6.40639 1.23219V7.26394ZM7.28091 7.2521L12.3627 4.24782L7.28091 1.24353V7.2521Z"
                          fill="black"/>
                </svg>
                Seekube
            </Link>
            by
            <Link
                    preview="hellowork.png"
                    description="HelloWork Group est le premier acteur digital français de l’emploi, du recrutement et de la formation. A travers ses différentes solutions, le groupe accompagne les actifs tout au long de leur vie professionnelle, les entreprises, cabinets de recrutement et les centres de formation/écoles sur la valorisation de leurs offres de formation."

                    href="https://hellowork.com" target="_blank">
                <svg height="18" style="margin-right: 4px; margin-bottom: -2px" viewBox="0 0 14 16" fill="none"
                     xmlns="http://www.w3.org/2000/svg">
                    <path fill-rule="evenodd" clip-rule="evenodd"
                          d="M2.96035 6.62426V6.63994L0.000723308 6.6435V6.62497C0.00619575 4.86697 0.708529 3.18288 1.95376 1.94192C3.199 0.700965 4.88549 0.00441781 6.64349 0.00499245V0H6.90797C8.6659 0.00678161 10.3496 0.709289 11.5911 1.95394C12.8325 3.1986 13.5307 4.88414 13.5329 6.64208H10.5712C10.5714 5.66827 10.1858 4.73402 9.49892 4.04377C8.812 3.35351 7.87964 2.96345 6.90584 2.95893H6.64423C5.67041 2.95891 4.73618 3.34449 4.04585 4.03135C3.35552 4.7182 2.96525 5.65045 2.96035 6.62426ZM2.95962 9.37432V9.35863L0 9.35649V9.37502C0.00547276 11.1331 0.707913 12.8173 1.9533 14.0583C3.19869 15.2993 4.88538 15.9958 6.64351 15.995V16H6.90795C8.66612 15.9934 10.3502 15.2909 11.5918 14.0461C12.8334 12.8012 13.5316 11.1154 13.5337 9.35721H10.5712C10.5712 10.331 10.1855 11.2651 9.49867 11.9553C8.8118 12.6455 7.87956 13.0356 6.90582 13.0404H6.64421C5.67014 13.0406 4.73567 12.655 4.04517 11.9679C3.35467 11.2809 2.96433 10.3484 2.95962 9.37432Z"
                          fill="#161615"/>
                </svg>
                Hellowork Group
            </Link>
            où j'apporte ma contribution pour aider les gens à
            dénicher leur futur <BriefCase strokeWidth="1.6"/> emploi.
          <br/><br/>
            En parallèle, j'ai lancé un produit qui me tient à cœur :
            <Link
                    preview="blober.png"
                    description="Blober révolutionne la manière dont vous racontez des histoires en ligne. Nous simplifions la création de webstories pour enrichir votre contenu, optimiser la communication et engager votre audience. Pas de codage, pas de tracas, juste un storytelling fluide et efficace pour tous les domaines, du marketing au milieu culturel."
                  href="https://blober.app" target="_blank">
                <svg width="18" height="16" style="margin-right: 4px; margin-bottom: -2px" viewBox="0 0 18 18"
                     fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path fill-rule="evenodd" clip-rule="evenodd"
                          d="M0 0.818176H2.86364V5.53763C3.86209 4.88162 5.05693 4.49999 6.34091 4.49999C9.8429 4.49999 12.6818 7.33891 12.6818 10.8409C12.6818 14.3429 9.8429 17.1818 6.34091 17.1818C2.83892 17.1818 0 14.3429 0 10.8409C0 10.7113 0.00389515 10.5826 0.0115606 10.4549L0 10.4318V0.818176ZM6.54545 14.7273C4.51203 14.7273 2.86364 13.0789 2.86364 11.0454C2.86364 9.01203 4.51203 7.36363 6.54545 7.36363C8.57887 7.36363 10.2273 9.01203 10.2273 11.0454C10.2273 13.0789 8.57887 14.7273 6.54545 14.7273ZM11.6591 17.1818C10.9021 17.1818 10.1762 17.0492 9.50314 16.8059C9.82338 16.6358 10.1283 16.4406 10.4153 16.223C10.815 16.315 11.2314 16.3636 11.6591 16.3636C14.7092 16.3636 17.1818 13.891 17.1818 10.8409C17.1818 7.79078 14.7092 5.31818 11.6591 5.31818C11.231 5.31818 10.8147 5.36675 10.4151 5.45867C10.1282 5.24114 9.82332 5.04602 9.50314 4.87593C10.1762 4.63263 10.9021 4.49999 11.6591 4.49999C15.1611 4.49999 18 7.33891 18 10.8409C18 14.3429 15.1611 17.1818 11.6591 17.1818ZM11.8636 15.5455C11.6467 15.5455 11.4334 15.5301 11.2247 15.5004C11.455 15.2591 11.6677 15.0006 11.8605 14.7273L11.8636 14.7273C13.897 14.7273 15.5454 13.0789 15.5454 11.0454C15.5454 9.10274 14.0408 7.51147 12.1334 7.37336C11.9611 7.08628 11.7682 6.81305 11.5565 6.55576C11.658 6.54892 11.7604 6.54545 11.8636 6.54545C14.3489 6.54545 16.3636 8.56016 16.3636 11.0454C16.3636 13.5307 14.3489 15.5455 11.8636 15.5455ZM8.18181 4.34499C7.91541 4.26964 7.64232 4.21024 7.36363 4.16788V1.63636H6.13635V4.09395C5.85914 4.1022 5.58609 4.12719 5.31817 4.16793V1.63636V0.818176H6.13635H7.36363H8.18181V1.63636V4.34499Z"
                          fill="black"/>
                </svg>
                Blober.app
            </Link>
        </div>

    </div>
{/if}
<style>

    .accent {
        color: var(--slate-500);
    }

    .header {
        font-size: 18px;
        line-height: 34px;
    }

    :global(.header svg) {
        display: inline;
        margin-bottom: -4px;
        width: auto;
    }

    img {
        height: 100px;
        background: white;
        border: 1px solid var(--slate-200);
        overflow: hidden;
        border-radius: 100px;
    }

    .header__title {
        line-height: 150%;
        display: flex;
        gap: 16px;
        place-items: center;
        height: 160px;
        margin-bottom: 16px;
    }
</style>