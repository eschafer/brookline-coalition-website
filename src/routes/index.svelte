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

<section class="grid-container usa-section">
  <div class="grid-row grid-gap">
    <div class="tablet:grid-col-4">
      <h2 class="font-heading-xl margin-top-0 tablet:margin-bottom-0">
        <span style="font-weight: 900; vertical-align: super">Step up,</span> <span style="font-weight: 300; vertical-align: sub">step&nbsp;back</span>
      </h2>
    </div>
    <div class="tablet:grid-col-8 usa-prose">
      <!--<p>
        We are a coalition of neighbors and community organizers committed to electing progressives to all positions in Town government to achieve the <b>boldly progressive</b> changes Brookline wants and needs.
      </p>-->
      <p>The Brookline Equity Coalition is a grassroots political action organization that <mark>promotes equity and justice in our community through an anti-racist lens</mark>. We make space for marginalized voices to step up and <a href="/get-involved" class="usa-link">get involved</a>, and encourage those with privilege to step back in support.</p>
      <p>We are committed to <a href="/endorsements">electing progressive candidates</a> to all positions in Town government to achieve the boldly progressive changes Brookline wants and needs.</p>

      <!--<p>We <b>recruit and support bold, progressive candidates in local elections</b>, who will challenge the status quo for a more equitable Brookline.</p>-->
    </div>
  </div>
</section>

<!--<section class="usa-graphic-list usa-section usa-section--light">
  <div class="grid-container">
    <div class="usa-graphic-list__row grid-row grid-gap">
      <div class="usa-media-block tablet:grid-col">
        <img
          class="usa-media-block__img"
          src="/assets/img/circle-124.png"
          alt=""
        />
        <div class="usa-media-block__body">
          <h2 class="usa-graphic-list__heading">
            Our values
          </h2>
          <p>
            <q>Progressive</q> means different things to different people. To our organizers and candidates, progressive means taking real action to bring material, systemic change for racial, social, environmental, and economic justice.
          </p>
        </div>
      </div>
      <div class="usa-media-block tablet:grid-col">
        <img
          class="usa-media-block__img"
          src="/assets/img/circle-124.png"
          alt=""
        />
        <div class="usa-media-block__body">
          <h2 class="usa-graphic-list__heading">
            Our goals
          </h2>
          <p>
            We aim to achieve majorities in Town government willing to pass legislation in keeping with our values.
          </p>
        </div>
      </div>
    </div>
  </div>
</section>-->

<style>
  mark {
    font-weight: 500;
    background-color: #FFD500;
  }

  .usa-prose {
    font-size: 1.125rem;
  }

  a, a:visited {
    color: #d7008e;
    font-weight: 600;
  }
</style>