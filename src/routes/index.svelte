<svelte:head>
  <title>Brookline Equity Coalition</title>
  <meta name="description" content="Brookline Equity Coalition is a grassroots group of neighbors and community organizers committed to electing progressives to all positions in Town government.">
</svelte:head>

<script context="module">
  export const prerender = true;
</script>

<script>
  import { onMount } from 'svelte';

  onMount(async () => {
    if (window.netlifyIdentity) {
      window.netlifyIdentity.on("init", user => {
        if (!user) {
          window.netlifyIdentity.on("login", () => {
            document.location.href = "/admin/";
          });
        }
      });
  }

  });
</script>

<h1 class="usa-sr-only">Brookline Equity Coalition</h1>

<section class="grid-container usa-section usa-prose">
  <div class="grid-row grid-gap">
    <div class="tablet:grid-col-4">
      <h2 class="font-heading-xl margin-top-0 tablet:margin-bottom-0">
        Who we are.
      </h2>
    </div>
    <div class="tablet:grid-col-8">
      <p>We, the Brookline Equity Coalition (BEC), are a grassroots group of community members. Our goal is to attain progressive municipal policies and governance here in Brookline.</p>

      <p>It is our belief that Brookline deserves a town government with strong progressive values. As progressives, we advocate for:</p>
      <dl>
          <dt>Improving the health & wellbeing of residents.</dt>
          <dd>Funding food security, older adult services, the repair of public housing units, and public education.</dd>

          <dt>Forward-looking, community-driven planning.</dt>
          <dd>Prioritizing addressing the climate crisis, affordable housing, increasing civic participation, meeting residents' needs, and a grassroots approach to charter change.</dd>

          <dt>Principled, open-minded leadership.</dt>
          <dd>Always factoring in racial justice, representation for all genders, LGBTQIA+ liberation, the need for intersectionality, reproductive justice, and support for workers and labor unions.</dd>

          <dt>Good governance.</dt>
          <dd>Ensuring seats at the table for the typically under-represented, meeting the needs of individuals with disabilities or with limited English proficiency, budgeting that reflects progressive priorities, and predictable and regularly scheduled operating overrides.</dd>
      </dl>

      <p>(For more detail, see <a href="/values" class="usa-link">our values</a>.)</p>

    </div>
  </div>
  <div class="grid-row grid-gap">
    <div class="tablet:grid-col-4">
      <h2 class="font-heading-xl margin-top-0 tablet:margin-bottom-0">
        Making Brookline a progressive town.
      </h2>
    </div>
    <div class="tablet:grid-col-8">
      <p>Here is a list of <a href="/endorsements" class="usa-link">our members and endorsed elected officials</a>. We are your neighbors, and we welcome you to join us in helping to create a town that prioritizes progressive values and policies!</p>
      <p>Learn about <a href="/get-involved" class="usa-link">how to get involved</a>.</p>
    </div>
  </div>
</section>

<style>
  dt {
    font-weight: 700;
  }
</style>