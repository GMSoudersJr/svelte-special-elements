<script lang="ts">
  interface NavItem {
    href: string;
    innerHtml: string;
  };

  export let navList: ArrayLike<NavItem>;
</script>

<nav>
  <ul>
     {#each navList as navItem}
       <li class="fancy"> 
         <slot prop={navItem} />
       </li>
     {/each}
  </ul>
</nav>

<style>
  ul .fancy {
    list-style-type: none;
    text-align: center;
  }
</style>

