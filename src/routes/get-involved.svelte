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

      <h2>Get endorsed by us and/or join us as an organizer.</h2>

      <p>If you are running for Town Meeting in Brookline, and are interested in joining the Brookline Equity Coalition and/or being endorsed by us, please fill out <a href="https://docs.google.com/forms/d/e/1FAIpQLScc2Kq-4wySgkvl0yTX8B_ridMRUuIlXve2MlS8yIIQPOH5yg/viewform" class="usa-link usa-link--external">this Google Form</a>. Additionally, if you are not a candidate for office but wish to join our group as an organizer, you are also welcome to fill out the form.</p>
      <p>Note that we will look at political contribution history, previous endorsements (of and by you), past public statements, and voting records (if you're an incumbent).</p>
      <p>We understand that everyone's politics can evolve, so rather than judge someone according to a single statement or decision, we will consider the totality of information available.</p>
      <p>Membership in the Brookline Equity Coalition — or an endorsement from us — does not obligate a candidate to mutually endorse all of our other Town Meeting candidates.</p>
      <p>However, with respect to the upcoming State Rep race in the 15th Norfolk district, the B.E.C. sees vast differences between the two current candidates that are impossible to ignore.</p>
      <p>We see the Select Board's Vice Chair, <a href="https://www.raulforrep.com/" class="usa-link usa-link--external">Raul Fernandez</a>, as someone willing to challenge the status quo — and the Massachusetts State House is in dire need of more individuals willing to <a href="https://actonmass.org/the-campaign" class="usa-link usa-link--external">speak truth to power</a>. In Fernandez, we also see an advocate for climate justice, racial justice, and economic justice; in other words, someone with a comprehensive understanding of inequality.</p>
      <p>Therefore, we ask Brookline Equity Coalition members to side with Fernandez in the September 6th State primary election.</p>
    
      <h2>What joining the Brookline Equity Coalition as a member means</h2>

      <p>We are trying to build an organizing space for community members who wish to help enact boldy progressive changes in Brookline. It's our aim to maintain a space that is inclusive, accessible, and democratic — but that is also safe from those whose intentions run counter to the progressive values outlined on our charter.</p>
      <p>If you're interested in joining our meetings (about three times a month), we welcome you to apply. Membership costs nothing, we only ask that anyone who would like to join our group be willing to sign <a href="https://docs.google.com/document/d/1HNjhQmXgDeEjLw1jmZ5goAd53OfyHCFmYfxMp_zm0U0/edit" class="usa-link usa-link--external">our charter</a>.</p>
      <p>There also is no obligation to attend 100% of our meetings. We understand that people live busy lives and have many obligations already. So, we welcome whatever level of engagement you are ready to provide.</p>
    </div>
  </div>
</section>

<style>
</style>