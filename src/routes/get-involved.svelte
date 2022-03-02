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



      <h2>Join us as an organizer.</h2>

      <p>Individuals who are not running for office can join the Brookline Equity Coalition (BEC) as an organizer.</p>
      <p>To join, send an email to <a href="mailto:RBcampaignEmail@gmail.com" class="usa-link usa-link--external">RBcampaignEmail@gmail.com</a> affirming you agree with <a href="/values" class="usa-link">our values</a>. In your message, please also tell us a little about yourself and why you wish to get involved.</p>
      <p>Please note that we feel an obligation to ensure our group is an organizing space safe from those whose intentions run counter to progressive values. Individuals who are known to be campaigning for conservative or reactionary candidates and causes, and/or undermining progressive efforts will not be permitted admittance.</p>
      

      <h2>Get endorsed by us and become a member.</h2>

      <p>If you are running for Town Meeting in Brookline, and are interested in joining BEC and/or being endorsed by us, please fill out <a href="https://docs.google.com/forms/d/e/1FAIpQLSccRojH6z-aqGKuD9vOuqUQ7I0T-C0eVtH4xcHMhjlSILDXIQ/viewform" class="usa-link usa-link--external">this Google Form</a>.</p>
      <p>Note that we will look at political contribution history, previous endorsements (of and by you), past public statements, and voting records (if you're an incumbent).</p>
      <p>We understand that everyone's politics can evolve, so rather than judge someone according to a single statement or decision, we will consider the totality of information available.</p>
      <p>Membership in BEC — or an endorsement from us — does not obligate a candidate to mutually endorse all of our other Town Meeting candidates.</p>
      <p>However, with respect to the upcoming State Rep race in the 15th Norfolk district, the B.E.C. sees vast differences between the two current candidates that are impossible to ignore.</p>
      <p>We see the Select Board's Vice Chair, <a href="https://www.raulforrep.com/" class="usa-link usa-link--external">Raul Fernandez</a>, as someone willing to challenge the status quo — and the Massachusetts State House is in dire need of more individuals willing to <a href="https://actonmass.org/the-campaign" class="usa-link usa-link--external">speak truth to power</a>. In Fernandez, we also see an advocate for climate justice, racial justice, and economic justice; in other words, someone with a comprehensive understanding of inequality.</p>
      <p>Therefore, we ask BEC members to side with Fernandez in the September 6th State primary election.</p>
    </div>
  </div>
</section>

<style>
</style>