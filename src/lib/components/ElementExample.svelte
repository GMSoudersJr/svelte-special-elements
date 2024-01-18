<script lang="ts">
	import SlotWidget from "./SlotWidget.svelte";

  const options = [
    {
      value: "blockquote",
      innerHtml: "blockquote"
    },
    {
      value: "code",
      innerHtml: "code"
    },
    {
      value: "h1",
      innerHtml: "h1"
    },
    {
      value: "h2",
      innerHtml: "h2"
    },
    {
      value: "h3",
      innerHtml: "h3"
    },
    {
      value: "h4",
      innerHtml: "h4"
    },
    {
      value: "h5",
      innerHtml: "h5"
    },
    {
      value: "h6",
      innerHtml: "h6"
    },
    {
      value: "i",
      innerHtml: "i"
    },
    {
      value: "p",
      innerHtml: "p"
    },
    {
      value: "q",
      innerHtml: "q"
    },
    {
      value: "s",
      innerHtml: "s"
    },
    {
      value: "small",
      innerHtml: "small"
    },
    {
      value: "strong",
      innerHtml: "strong"
    },
    {
      value: "sub",
      innerHtml: "sub"
    },
    {
      value: "sup",
      innerHtml: "sup"
    },
    {
      value: "u",
      innerHtml: "u"
    },
  ];
  $: tag = selected;
  let selected: string;
</script>

<SlotWidget>
  <svelte:fragment slot="header">
    <label for="element">
      Select an HTML Element:
      <select
        name="element"
        id="element"
        bind:value={selected}
      >
        {#each options as option}
          <option value={option.value}>{option.innerHtml}</option>
        {/each}
      </select>
    </label>
  </svelte:fragment>
  <p slot="disclaimer">Example:</p>
  <svelte:element this={tag} slot="content">
    This is an HTML <code>{tag}</code> Element
  </svelte:element>
  <p slot="footer">Copyright (c) 2024 Gerald Souders</p>
</SlotWidget>

<style>
  label {
    display: grid;
    grid-template-columns: max-content min-content;
    align-items: baseline;
    justify-content: center;
    column-gap: 4px;
    padding-bottom: 2px;
  }
</style>
