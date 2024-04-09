<script>
    import Header from "$lib/Parts/Header.svelte";
    import Projects from "$lib/Parts/Projects.svelte";
    import Experiences from "$lib/Parts/Experiences.svelte";
    import {quartInOut} from "svelte/easing";
    import { fly } from 'svelte/transition';
    import {onMount} from "svelte";

    let ready = false;
    onMount(() => ready = true);

</script>

<div class="bg">
    <div class="square"></div>

    <div class="container">
        <Header />
        <div class="list">
        <Projects />
        <Experiences />
        </div>
    </div>
    {#if ready}
        <div transition:fly={{ delay: 900, duration: 500 , y: 50, easing: quartInOut }}
             style="display: flex; justify-content: center; flex-direction: column; width: 100vw; align-items: center; gap: 8px; margin-bottom: 64px">
        <div style=" color : var(--slate-500); margin-top: 64px; font-size: 14px; line-height: 150%; text-align: center;">
            Merci de votre visite.
        </div>
        <img src="logo.png" height="100" width="100" style="opacity: 0.6;" />
        </div>
    {/if}
</div>
<style>
    .bg {
        position: absolute;
        top: 0;
        width: 100vw;
        height: 100vh;
        background-image: radial-gradient(100% 50% at 50% 0,rgba(32,148,243,.17) 0,rgba(32,148,243,0) 50%,rgba(32,148,243,0) 100%);
    }

    .square {
        opacity: 0.25;
        color: hsl(0 0% 3.9%);
        font-style: normal;
        box-sizing: border-box;
        border: 0 solid hsl(0 0% 89.8%);
        position: absolute;
        bottom: 0;
        left: 0;
        right: 0;
        top: 0;
        background-image: linear-gradient(90deg,#4f4f4f2e 1px,transparent 0),linear-gradient(180deg,#4f4f4f2e 1px,transparent 0);
        background-size: 22px 22px;
        mask-image: radial-gradient(ellipse 90% 50% at 50% 0,#000 70%,transparent 110%);
    }
    .container {
        padding: 2rem;
        max-width: 750px;
        width: 100%;
        margin: 0 auto;
        position: relative;
    }
    .list {
        display:flex;
        gap : 64px
    }

    @media (max-width: 750px) {
        .list {
           flex-direction: column;
            gap : 16px

        }
    }
</style>