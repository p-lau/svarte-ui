<script lang="ts">
    export let brand: string = undefined;
    export let show: boolean = true;
    export let sticky: boolean = true;
    let wWidth = undefined;
</script>

<svelte:window bind:innerWidth={wWidth}/>

{#if show}
    <header class:sticky class:header={true} {...$$restProps}>
        <slot name="brand">
            <span>{brand}</span>
        </slot>
        <slot name="menu"/>
    </header>
{/if}

<style>
    .header {
        height: var(--sv-nav-h);
        background-color: var(--sv-bg-accent);
        border-bottom: var(--sv-nav-border);
        display: var(--sv-nav-display);
    }

    .sticky {
        position: sticky;
    }
</style>