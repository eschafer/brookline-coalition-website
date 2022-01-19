<script>
  export let classes = '';
  export let id = '';
  export let name = '';
  export let value = '';
  export let label = '';
  export let labelDescription = '';
  export let checked = false;
  export let disabled = false;
</script>

<div class="usa-checkbox">
  <input
    class={`${classes} usa-checkbox__input`}
    id={id}
    type="checkbox"
    name={name}
    value={value}
    checked={checked ? 'checked' : undefined}
    disabled={disabled ? 'disabled' : undefined}
  />
  <label
    class="usa-checkbox__label"
    for={id}
  >
    {label}
    {#if labelDescription}
      <span class="usa-checkbox__label-description">
        {labelDescription}
      </span>
    {/if}
  </label>
</div>
