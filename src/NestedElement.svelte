<svelte:options tag="nested-element" />

<script lang="ts">
  /* Svelte will treat props as WebComponent attributes, which allows them to be reactive. */
  let className: string;

  export { className as class };
</script>

<p class={className}>A nested element.</p>
<slot />
