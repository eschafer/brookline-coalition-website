<script>
  export let classes = null;
  export let ariaLabel = 'Breadcrumbs';
  export let items = [];
</script>

{#if items.length > 0}
  <nav
    class={`usa-breadcrumb ${classes || ''}`}
    aria-label={ariaLabel ? ariaLabel : undefined}
  >
    <ol class="usa-breadcrumb__list">
      {#each items as item, i (item.id)}
        <li
          class={`usa-breadcrumb__list-item${(i === items.length - 1) ? ' usa-current' : ''}`}
          aria-current={(i < items.length - 1) ? undefined: 'page'}
        >
          {#if i < items.length - 1}
            <a href={item.href} class="usa-breadcrumb__link">
              <span>{item.title}</span>
            </a>
          {:else}
            <span>{item.title}</span>
          {/if}
        </li>
      {/each}
    </ol>
  </nav>
{/if}
