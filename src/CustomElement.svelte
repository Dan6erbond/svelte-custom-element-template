<svelte:options tag="my-custom-element" />

<script lang="ts">
  import { get_current_component } from "svelte/internal";
  /* Nested elements need to be used as custom elements. */
  import "./NestedElement.svelte";

  /* Web component events can be dispatched with this typed helper. */
  const thisComponent = get_current_component();
  function dispatchWcEvent<T>(name: string, detail: T) {
    thisComponent.dispatchEvent(
      new CustomEvent(name, {
        detail, // detail allows us to pass custom data
        composed: true, // propagate across the shadow DOM
      }),
    );
  }

  /* Reactivity works as usual in Svelte. */
  let counter = 0;
</script>

<main>
  <h1>Hello World!</h1>
  <p>
    Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte
    apps.
  </p>
  <!-- Button click emits a custom web component event, we need to use a name that doesn't collide with standard HTML events (such as 'click'). -->
  <button on:click={() => dispatchWcEvent("custom-click", { detail: "test" })}>Click Me!</button>
  <nested-element class="custom-class-name">
    <!-- Slots work as usual in Svelte. -->
    <button on:click={() => counter++}> Counter: {counter}</button>
  </nested-element>
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
