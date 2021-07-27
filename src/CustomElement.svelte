<svelte:options tag="my-custom-element" />

<script lang="ts">
  /* Nested elements need to be used as custom elements. */
  import "./NestedElement.svelte";
</script>

<main>
  <h1>Hello World!</h1>
  <p>
    Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte
    apps.
  </p>
  <nested-element class="custom-class-name" />
</main>

<style>
  /* Svelte will purge unused CSS classes, so they cannot be passed down to other components. */

  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
