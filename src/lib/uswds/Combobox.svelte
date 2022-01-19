<script>
  export let options = [];
  export let label = '';
  export let id = '';
  export let name = '';
</script>

<label
  class="usa-label"
  for={id}
>
  {label}
</label>
<div class="usa-combo-box">
  <select
    class="usa-select"
    name={name}
    id={id}
  >
    {#each options as option}
      <option
        value={option.value}
      >
        {option.label}
      </option>
    {/each}
  </select>
</div>
