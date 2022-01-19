<script>
  export let classes = '';
  export let mediaClasses = '';
  export let heading = '';
  export let mediaSrc = '';
  export let mediaAlt = '';
  export let body = '';
  export let footer = '';
</script>

<li class={`${classes} usa-card`}>
  <div class="usa-card__container">
    <header class="usa-card__header">
      <h2 class="usa-card__heading">{heading}</h2>
    </header>
    {#if mediaSrc && mediaAlt}
      <div class={`${mediaClasses} usa-card__media`}>
        <div class="usa-card__img">
          <img
            src={mediaSrc}
            alt={mediaAlt}
          />
        </div>
      </div>
    {/if}
    <div class="usa-card__body">
      <p>{body}</p>
    </div>
    <div class="usa-card__footer">
      <button class="usa-button">{footer}</button>
    </div>
  </div>
</li>
