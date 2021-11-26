<script lang="ts">
    /** Set to `true` to disable the accordion */
    export let disabled = false;

    /** Set to `true` to display the skeleton state */
    export let skeleton = false;

    import { setContext } from "svelte";
    import { writable } from "svelte/store";
    import AccordionSkeleton from "./Skeleton.svelte";

    const disableItems = writable(disabled);

    $: disableItems.set(disabled);

    setContext("Accordion", { disableItems });
</script>
  
  <!-- svelte-ignore a11y-mouse-events-have-key-events -->
  {#if skeleton}
    <AccordionSkeleton
      {...$$restProps}
      on:click
      on:mouseover
      on:mouseenter
      on:mouseleave
    />
  {:else}
    <ul
      {...$$restProps}
      on:click
      on:mouseover
      on:mouseenter
      on:mouseleave
    >
      <slot />
    </ul>
  {/if}