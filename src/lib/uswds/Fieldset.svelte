<script>
  export let legend = '';
  export let hint = '';
  export let hintId = '';
</script>

<fieldset class="usa-fieldset">
  <legend class="usa-legend">
    {legend}
  </legend>
  {#if hint}
    <span class="usa-hint" id={hintId}>{hint}</span>
  {/if}
  <slot></slot>
</fieldset>
