<div class="example">
  <slot name="header">
    <h1>Widget Without Header</h1>
  </slot>
  {#if $$slots.disclaimer}
    <hr />
    <slot name="disclaimer" />
  {/if}
  <slot name="content">
    <p>No content provided</p>
  </slot>
  <slot name="footer" />
</div>
