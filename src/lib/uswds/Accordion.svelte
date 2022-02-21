<script>
  import { v4 as uuidv4 } from 'uuid';

  // default: borderless
  // `bordered`: adds visual border
  export let variant = null;

  // lets you open multiple sections at the same time
  export let multiselectable = false;
  
  // array of item objects:
  // id: unique string
  // expanded: boolean for start state
  // title: string
  // content: string (or html string)
  export let items = [];

  // links button with content
  // each accordion needs a unique id
  export let id_prefix = `${uuidv4()}--`;
</script>

{#if items.length > 0}
  <div
    class={`usa-accordion${variant ? ` usa-accordion--${variant}` : ''}`}
    aria-multiselectable={multiselectable === true ? 'true' : undefined}
  >
    {#each items as item (item.id)}
      <!-- Use the accurate heading level to maintain the document outline -->
      <h4 class="usa-accordion__heading">
        <button
          class="usa-accordion__button"
          aria-expanded={`${item.expanded && item.expanded === true ? 'true' : 'false'}`}
          aria-controls={`${id_prefix}${item.id}`}
        >
          {item.title}
        </button>
      </h4>
      <div
        id={`${id_prefix}${item.id}`}
        class="usa-accordion__content usa-prose"
      >
        {@html item.content}
      </div>
    {/each}
  </div>
{/if}
