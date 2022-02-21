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
        Who are we?
      </h2>
    </div>
    <div class="tablet:grid-col-8">
      <p>We, the Brookline Equity Coalition (BEC), are a grassroots group of community members. Our goal is to achieve majorities in municipal government during the <a href="/town-election" class="usa-link">Tuesday, May 3rd Town election</a> (and beyond) willing to pass and implement progressive policies.</p>
      <p>It is our belief that the voters of Brookline are far more progressive than what their current representation is providing them. To our group, “progressive” means fighting for policies that would:</p>
      <ul>
        <li>Fully fund services for older adults.</li>
        <li>Fervently address the climate crisis.</li>
        <li>Improve municipal government structures.</li>
        <li>Support hybrid (in-person + virtual) meeting options.</li>
        <li>Refurbish and renovate public housing units.</li>
        <li>Fight food insecurity with Town resources.</li>
        <li>Build truly affordable housing that prioritizes people and community, not profit.</li>
        <li>Provide ample resources for public school students and educators.</li>
        <li>Recognize how social and economic inequalities are interconnected.</li>
        <li>Reimagine public safety to mean proactively fulfilling people's social, health-related, and economic needs.</li>
        <li>Fully accommodate residents with limited English proficiency.</li>
        <li>Address the needs and interests of residents with disabilities.</li>
        <li>Fight bias and discrimination along the lines of race, gender identity, and sexuality.</li>
        <li>Meet the needs of renters, a critically under-represented constituency in Town government.</li>
        <li>[See more on our “Values” page]</li>
      </ul>
      <p>We humbly ask for your support of our <a href="/endorsements" class="usa-link">endorsed candidates</a> in Brookline's <strong>May 3rd Election</strong> so that we can fight in Town government to attain such progressive policies.</p>
      <p>Furthermore, we encourage anyone who agrees with the above policies to consider getting involved in our organizing and maybe even run for Town Meeting yourself! Learn about <a href="/get-involved" class="usa-link">how to get involved</a>.</p>
    </div>
  </div>
</section>
