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
<div class="outer grid-container">
  <div class="inner">
    <h1>{specialElement.toUpperCase()}</h1>
    <svelte:component this={example[specialElement]} />
  </div>
</div>

<style>
  .outer {
    max-width: 90vw;
    padding: 4px;
    border-radius: 16px;
    background: rgb(2,0,36);
    background: linear-gradient(215deg, rgba(2,0,36,1) 0%, rgba(203,43,213,0.915954415954416) 26%, rgba(0,212,255,1) 100%);
  }
  .inner {
    border-radius: 12px;
    background-color: white;
    display: grid;
    row-gap: 1rem;
    padding-top: 1rem;
    padding-bottom: 1.618rem;
  }
</style>
