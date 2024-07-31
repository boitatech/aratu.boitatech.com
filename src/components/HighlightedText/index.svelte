<script>
    import { onMount, createEventDispatcher } from 'svelte';

    export let value = "";
    let highlightedText = '';
    let interval;

    const dispatch = createEventDispatcher();

    onMount(() => {
        startAnimation();
    });

    function startAnimation() {
        let index = 0;
        interval = setInterval(() => {
            highlightedText = value.slice(0, index);
            index++;
            if (index > value.length) {
                clearInterval(interval);
            }
        }, 100); 
    }
</script>

<style>
    @import './index.css';
</style>

{#each [...value] as char, i}
    {#if i < highlightedText.length}
        <span class="highlight">{char}</span>
    {:else}
        {char}
    {/if}
{/each}