<script lang="ts">
  import "../app.css";
  import { navList } from "$lib/navList";
	import NavList from "$lib/components/NavList.svelte";

</script>

<main>
  <h1 class="col-t-12 col-d-12">Svelte Special Elements Playground</h1>
  <NavList {navList} let:prop={navItem}>
    <a href={navItem.href}>
      <code>
        {navItem.innerHtml}
      </code>
    </a>
  </NavList>
  <section>
    <slot>
    </slot>
  </section>
</main>

<style>
  main {
    width: 100vw;
    display: grid;
    grid-template-rows: repeat(2, min-content)  1fr;
    justify-content: center;
    justify-items: stretch;
  }
  section {
    display: grid;
    justify-content: stretch;
    text-align: center;
  }
  ul {
    text-align: center;
  }
  li {
    list-style: none;
  }
  a {
    text-decoration: none;
  }
</style>
