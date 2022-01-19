<script>
  export let hintId = '';
</script>

<div class="usa-memorable-date">
  <div class="usa-form-group usa-form-group--month">
    <label class="usa-label" for="date_1">Month</label>
    <input
      class="usa-input"
      aria-describedby={hintId}
      id="date_1"
      name="date_1"
      type="text"
      maxlength="2"
      pattern="[0-9]*"
      inputmode="numeric"
      value=""
    />
  </div>
  <div class="usa-form-group usa-form-group--day">
    <label class="usa-label" for="date_2">Day</label>
    <input
      class="usa-input"
      aria-describedby={hintId}
      id="date_2"
      name="date_2"
      type="text"
      maxlength="2"
      pattern="[0-9]*"
      inputmode="numeric"
      value=""
    />
  </div>
  <div class="usa-form-group usa-form-group--year">
    <label class="usa-label" for="date_3">Year</label>
    <input
      class="usa-input"
      aria-describedby={hintId}
      id="date_3"
      name="date_3"
      type="text"
      minlength="4"
      maxlength="4"
      pattern="[0-9]*"
      inputmode="numeric"
      value=""
    />
  </div>
</div>
