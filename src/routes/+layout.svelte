<script lang="ts">
  import "../app.css";
  import { navList } from "$lib/navList";
	import NavList from "$lib/components/NavList.svelte";

</script>

<main>
  <h1 class="header">Svelte Special Elements</h1>
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
    min-height: 100dvh;
    display: grid;
    grid-template-rows: repeat(2, min-content)  1fr;
    justify-content: center;
    justify-items: stretch;
    background: rgb(2,0,36);
    background: linear-gradient(35deg, rgba(2,0,36,1) 0%, rgba(203,43,213,0.915954415954416) 26%, rgba(0,212,255,1) 100%);
    padding-bottom: 1rem;
  }
  .header {
    text-align: center;
  }
  section {
    height: min-content;
    display: grid;
    justify-content: stretch;
    text-align: center;
    padding-top: 1rem;
  }
  ul {
    text-align: center;
  }
  li {
    list-style: none;
  }
  a {
    text-decoration: none;
    color: #FFFFFF
  }
</style>
