<script>
    import {onMount} from 'svelte';
    import { offset, flip, shift } from "svelte-floating-ui/dom";
    import { createFloatingActions } from "svelte-floating-ui";
    import {cubicInOut} from "svelte/easing";
    import { fly,scale, fade } from 'svelte/transition';
    import ArrowUpRight from 'lucide-svelte/dist/svelte/icons/arrow-up-right.svelte'


    export const ssr = false;

    export let description
    export let preview
    export let title
    export let href

    let button
    const handleMouseMove = (event) => {
        const pos = button.getBoundingClientRect();
        const mx = event.clientX - pos.left - pos.width / 2;
        const my = event.clientY - pos.top - pos.height / 2;

        button.style.transform = `translate(${mx * 0.15}px, ${my * 0.25}px)`;
    };

    const handleMouseLeave = (event) => {
        button.style.transform = 'translate3d(0px, 0px, 0px)';
        showTooltip = false
    };


    const [ floatingRef, floatingContent ] = createFloatingActions({
            strategy: "absolute",
            placement: "top",
            middleware: [
                    offset(6),
                    flip(),
                    shift(),
            ]
    });

    let showTooltip = false;


</script>


{#if showTooltip}
        <div style="position:absolute" use:floatingContent class="tooltip" transition:fade={{ delay: 0, duration: 300 , easing: cubicInOut }}>
                {#if preview}
                        <img src="./preview/{preview}" />

                {/if}
                <div class="description">
                        <p>{description}</p>
                        {#if href}
                        <a href="">{href}</a>
                        {/if}
                </div>
        </div>
{/if}

        <a
                bind:this={button}
                on:mouseenter={() => showTooltip = true}
                use:floatingRef
                on:mousemove={handleMouseMove}
                on:mouseleave={handleMouseLeave} {href} {...$$restProps}><slot></slot></a>

<style>


    a {
        color: inherit;
        cursor: pointer;
        padding: 6px;
        transition: all .3s ease-out;
            display: inline-block;
            line-height: 100%;
    }

    :global(.link svg) {
        flex-shrink: 0;
        transition: all .3s cubic-bezier(0.860, 0.000, 0.070, 1.000);
    }

    a:hover {
        background: var(--slate-100);
        border-radius: 4px;
        text-decoration: none;
    }

    .tooltip {
            pointer-events: none;
            line-height: normal;
            background: white;
            border: 1px solid rgb(0 0 0 / 0.1);
            border-radius: 6px;
            box-shadow: 0 1px 3px 0 rgb(0 0 0 / 0.1), 0 1px 2px -1px rgb(0 0 0 / 0.1);
            display: flex;
            flex-direction: column;
            width: 380px;
            overflow: hidden;
            z-index: 20;
            transform-origin: bottom center;
    }

    .tooltip img {
            height: 150px;
            width: 100%;
            object-fit: cover;
            border-bottom: 1px solid var(--slate-200)

    }


    p {
            font-size: 14px;
            color: var(--slate-700);
    }

    .description {
            padding: 12px ;
            line-height: 110%;
    }

    .description a {
            padding: 0;
            margin-top: 12px;
            text-align: right;
            color: var(--slate-500);
            font-size: 14px;
            text-decoration: none;
    }

</style>