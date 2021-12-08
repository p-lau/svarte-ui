<script lang="ts">
    export let show = true;

    let wWidth = undefined;
</script>

<svelte:window bind:innerWidth={wWidth}/>
{#if show}
    <slot name="left"/> 
    <header {...$$restProps}>
        <slot name="nav">
            <nav>
                {wWidth}
            </nav>
        </slot>
    </header>
    <slot name="right"/>
{/if}