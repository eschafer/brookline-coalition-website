<svelte:head>
  <title>Get Involved — Brookline Equity Coalition</title>
  <meta name="description" content="Sign up for our mailing list, join as an organizer, or get endorsed by the Brookline Equity Coalition.">
</svelte:head>

<script context="module">
  export const prerender = true;
</script>

<script>
  let result = {};
  
  function handleSubmit(event) {
    let formData = new FormData(this);

    fetch("/", {
      headers: { "Content-Type": "application/x-www-form-urlencoded" },
      method: "POST",
      body: new URLSearchParams(formData).toString(),
    }).then(() => {
      result = {
        success: true
      };
    }).catch(error => {
      result = {
        success: false,
        error
      };
    })
  }
</script>

<section class="usa-section grid-container usa-prose">
  <div class="grid-row grid-gap">
    <div class="tablet:grid-col-4">
      <h1 class="margin-top-0">Get Involved</h1>
    </div>
    <div class="tablet:grid-col-8">
      <form
        on:submit|preventDefault={handleSubmit}
        name="subscribe-mailing-list"
        method="POST"
        data-netlify="true"
        class="usa-form usa-form--large"
      >
        <!-- this is needed to work with netlify forms -->
        <!-- https://docs.netlify.com/forms/setup/#work-with-javascript-rendered-forms -->
        <input type="hidden" name="form-name" value="subscribe-mailing-list" />

        <fieldset class="usa-fieldset">
          <legend class="usa-legend usa-legend--large">
            Sign up for our mailing list
          </legend>
          
          <label class="usa-label" for="email">
            Email address
          </label>
          <input
            class="usa-input"
            id="email"
            name="email"
            type="email"
            autocapitalize="off"
            autocorrect="off"
            required
          />

          <input class="usa-button" type="submit" value="Sign up" />
        </fieldset>
      </form>

      {#if result.success === true}
        <div class="usa-alert usa-alert--success">
          <div class="usa-alert__body">
            <h4 class="usa-alert__heading">
              Thank you!
            </h4>
            <p class="usa-alert__text">
              We've added you to our list.
            </p>
          </div>
        </div>
      {:else if result.success === false}
        <div class="usa-alert usa-alert--error" role="alert">
          <div class="usa-alert__body">
            <h4 class="usa-alert__heading">Oh no!</h4>
            <p class="usa-alert__text">
              Something went wrong on our end. Please try again.
            </p>
          </div>
        </div>
      {/if}

      <h2>Interested in joining BEC?</h2>

      <p>We welcome you to join us in organizing for Brookline to be a town that prioritizes progressive values and policies. <a href="https://docs.google.com/forms/d/e/1FAIpQLSd8oUbsHFUKdJgj2NmD-bH2tFztGdXuXxcC3zXfxqrvDip1ig/viewform" class="usa-link usa-link--external">Here you can find our onboarding form</a>.</p>

      <h3>If you're an elected official</h3>

      <p>Please note that we will look at previous endorsements (of and by you), past public statements, political contribution history, and voting records. We understand that everyone's politics can evolve, so rather than judge someone according to a single statement or decision, we will consider the totality of information available.</p>

      <h3>Regarding the 15th Norfolk district primary</h3>

      <p>BEC members hold a variety of differing opinions on municipal topics. But to be transparent, with respect to the upcoming State Rep race in the 15th Norfolk district, BEC sees vast differences between the two current candidates that are impossible to ignore.</p>
      <p>We see <a href="https://www.raulforrep.com/" class="usa-link usa-link--external">Raul Fernandez</a> as someone willing to challenge the status quo — and the Massachusetts State House is in dire need of more individuals willing to speak truth to power. (It being one of the <a href="https://actonmass.org/the-campaign/" class="usa-link usa-link--external">least transparent and accountable legislatures in the nation</a>.) In Fernandez, we also see an advocate for climate justice, racial justice, and economic justice; in other words, someone with a comprehensive understanding of inequality.</p>
      <p>Therefore, we do ask Brookline Equity Coalition members to side with Fernandez in the September 6th State primary election.</p>
    </div>
  </div>
</section>

<style>
</style>