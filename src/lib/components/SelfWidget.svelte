<script lang="ts">
	import SlotWidget from "./SlotWidget.svelte";

  export let count: number;
</script>

{#if count > 0}
  <SlotWidget>
    <h1 slot="header">Same Slot Widget Using Self</h1>
    <p slot="disclaimer">This Element calls itself</p>
    <p slot="content">counting down... {count}</p>
  </SlotWidget>
  <svelte:self count={count - 1} />
{:else}
  <SlotWidget>
    <h1 slot="header">🚀 Self Example 🚀</h1>
    <p slot="disclaimer">Until the loop is finished</p>
    <p slot="content">Lift-off!</p>
  </SlotWidget>
{/if}
