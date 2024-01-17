<script lang="ts">
  import { page } from "$app/stores";
	import SelfExample from "$lib/components/SelfExample.svelte";
	import SlotExample from "$lib/components/SlotExample.svelte";
  import ComponentExample from "$lib/components/ComponentExample.svelte";
  import ElementExample from "$lib/components/ElementExample.svelte";
  import WindowExample from "$lib/components/WindowExample.svelte";
  import DocumentExample from "$lib/components/DocumentExample.svelte";
  import BodyExample from "$lib/components/BodyExample.svelte";
  import HeadExample from "$lib/components/HeadExample.svelte";
  import OptionsExample from "$lib/components/OptionsExample.svelte";
  import FragmentExample from "$lib/components/FragmentExample.svelte";

  interface Examples {
    [key: string]: typeof Page__SvelteComponent_;
  }

  const example: Examples = {
    slot: SlotExample,
    self: SelfExample,
    component: ComponentExample,
    element: ElementExample,
    window: WindowExample,
    document: DocumentExample,
    body: BodyExample,
    head: HeadExample,
    options: OptionsExample,
    fragment: FragmentExample,
  };

  $: specialElement = $page.params.specialElement;
</script>

<svelte:head>
  <title>
    Svelte Special Elements &lt;{$page.params.specialElement}&gt;
  </title>
</svelte:head>
<div class="background grid-container">
  <h1>{specialElement.toUpperCase()}</h1>
  <svelte:component this={example[specialElement]} />
</div>

<style>
  .grid-container {
    display: grid;
    max-width: 90vw;
    grid-template-rows: min-content;
    row-gap: 1rem;
    padding-top: 1rem;
    padding-bottom: 1.618rem;
  }
</style>
