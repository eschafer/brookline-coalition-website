<script>
  // usa-alert--info
  // usa-alert--success
  // usa-alert--warning
  // usa-alert--error
  // usa-alert--emergency
  //
  // usa-alert--info usa-alert--no-heading
  // usa-alert--info usa-alert--no-icon
  // usa-alert--info usa-alert--slim
  export let classes = '';
  export let role = null;
  export let title = null;
  export let content = '';
</script>

<div
  class={`usa-alert ${classes}`}
  role={role ? role : undefined}
>
  <div class="usa-alert__body">
    {#if title}
      <h4 class="usa-alert__heading">
        {title}
      </h4>
    {/if}
    <p class="usa-alert__text">
      {@html content}
    </p>
  </div>
</div>
