<svelte:head>
  <title>Our Values — Brookline Equity Coalition</title>
  <meta name="description" content="To our organizers and candidates, progressive means taking real action to bring material, systemic change for racial, social, environmental, and economic justice.">
</svelte:head>

<script context="module">
  export const prerender = true;
</script>

<script>
  import { onDestroy, onMount } from 'svelte';
  import Accordion from '$lib/uswds/Accordion.svelte';

  let accordion;
  let items = [
    {
      id: 'image-credits',
      title: 'Image credits',
      content: `<ul>
        <li><a href="https://www.flaticon.com/authors/chanut-is-industries">Icons created by Chanut-is-Industries - Flaticon</a></li>
        <li><a href="https://www.flaticon.com/authors/eucalyp">Icons created by Eucalyp - Flaticon</a></li>
        <li><a href="https://www.flaticon.com/authors/flat-icons">Icons created by Flat Icons - Flaticon</a></li>
        <li><a href="https://www.flaticon.com/authors/freepik">Icons created by Freepik - Flaticon</a></li>
        <li><a href="https://www.flaticon.com/authors/good-ware">Icons created by Good Ware - Flaticon</a></li>
        <li><a href="https://www.flaticon.com/authors/maxicons">Icons created by max.icons - Flaticon</a></li>
        <li><a href="https://www.flaticon.com/authors/monkik">Icons created by monkik - Flaticon</a></li>
        <li><a href="https://www.flaticon.com/authors/nhor-phai">Icons created by Nhor Phai - Flaticon</a></li>
        <li><a href="https://www.flaticon.com/authors/pixel-buddha-premium">Icons created by Pixel Buddha Premium - Flaticon</a></li>
        <li><a href="https://www.flaticon.com/authors/smashicons">Icons created by Smashicons - Flaticon</a></li>
      </ul>`
    },
  ];

  onMount(async () => {
    accordion = await import('uswds/src/js/components/accordion');
    
    accordion.on();
  });

  onDestroy(async() => {
    if (accordion) {
      accordion.off();
    }
  })
</script>

<div class="usa-section grid-container usa-prose">
  <h1>Our Values</h1>

  <p>To our organizers and candidates, <q>progressive</q> means taking real action to bring material, systemic change for racial, social, environmental, and economic justice.</p>

  <p>Progressive should mean — and has meant to our incumbent candidates — advocating for:</p>

  <h2>The improved health & wellbeing of residents</h2>

  <section class="usa-graphic-list usa-section">
    <div class="grid-container">
      <div class="usa-graphic-list__row grid-row grid-gap">
        <div class="usa-media-block tablet:grid-col">
          <img class="usa-media-block__img"  src="/img/icons/grocery.png" width="64" height="64" alt="">
          <div class="usa-media-block__body">
            <h3 class="usa-graphic-list__heading">Address food insecurity</h3>
            <p>Use Town resources to do so when required. A <a href="https://www.brooklinema.gov/DocumentCenter/View/28715/-Final-Report-2022-with-stakeholders" class="usa-link usa-link--external">recent study by the town (see “Food Access” section)</a> reveals that many community members struggle to secure a stable, nutritious diet — particularly low-income residents, BIPOC individuals, and older adults.</p>
          </div>
        </div>
        <div class="usa-media-block tablet:grid-col">
          <img class="usa-media-block__img"  src="/img/icons/van.png" width="64" height="64" alt="">
          <div class="usa-media-block__body">
            <h3 class="usa-graphic-list__heading">Fully fund services for older adults</h3>
            <p>Ensure institutions like the <a href="https://www.brooklineseniorcenter.org/" class="usa-link usa-link--external">Senior Center</a> are amply staffed and resourced, so older adults can age comfortably and healthily.</p>
          </div>
        </div>
      </div>
      <div class="usa-graphic-list__row grid-row grid-gap">
        <div class="usa-media-block tablet:grid-col">
          <img class="usa-media-block__img"  src="/img/icons/renovation.png" width="64" height="64" alt="">
          <div class="usa-media-block__body">
            <h3 class="usa-graphic-list__heading">Refurbish public housing units</h3>
            <p>Deal with the mold, pests, unmet repairs, and lack of basic appliances BHA tenants have reported. All Brookline residents deserve a healthy and safe living space.</p>
          </div>
        </div>
        <div class="usa-media-block tablet:grid-col">
          <img class="usa-media-block__img"  src="/img/icons/school-bag.png" width="64" height="64" alt="">
          <div class="usa-media-block__body">
            <h3 class="usa-graphic-list__heading">Provide ample resources for public school students and teachers</h3>
            <p>Commit to making the Brookline public school system more equitable, regardless of race, color, national origin, or income.</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <h2>Forward-looking, community-driven planning</h2>

  <section class="usa-graphic-list usa-section">
    <div class="grid-container">
      <div class="usa-graphic-list__row grid-row grid-gap">
        <div class="usa-media-block tablet:grid-col">
          <img class="usa-media-block__img"  src="/img/icons/town.png" width="64" height="64" alt="">
          <div class="usa-media-block__body">
            <h3 class="usa-graphic-list__heading">Deliver housing justice</h3>
            <p>Build more affordable housing; not just any housing, but specifically more homes affordable to traditionally excluded people and older adults, family public housing, co-ops, and community land trusts.</p>
          </div>
        </div>
        <div class="usa-media-block tablet:grid-col">
          <img class="usa-media-block__img"  src="/img/icons/charter.png" width="64" height="64" alt="">
          <div class="usa-media-block__body">
            <h3 class="usa-graphic-list__heading">Improve government structures</h3>
            <p>Explore processes like charter change and other structural shifts that could increase voter turnout and civic participation.</p>
          </div>
        </div>
      </div>
      <div class="usa-graphic-list__row grid-row grid-gap">
        <div class="usa-media-block tablet:grid-col">
          <img class="usa-media-block__img"  src="/img/icons/climate-change.png" width="64" height="64" alt="">
          <div class="usa-media-block__body">
            <h3 class="usa-graphic-list__heading">Address the climate crisis</h3>
            <p>Commit to such efforts with the urgency, magnitude, and social justice lens that it demands.</p>
          </div>
        </div>
        <div class="usa-media-block tablet:grid-col">
          <img class="usa-media-block__img"  src="/img/icons/brainstorm.png" width="64" height="64" alt="">
          <div class="usa-media-block__body">
            <h3 class="usa-graphic-list__heading">Reimagine public safety</h3>
            <p>Reallocate funds from the police budget to services that would better fulfill people's social, health-related, and economic needs — which would, in turn, improve public safety.</p>
          </div>
        </div>
      </div>
      <div class="usa-graphic-list__row grid-row grid-gap">
        <div class="usa-media-block tablet:grid-col">
          <img class="usa-media-block__img"  src="/img/icons/friends.png" width="64" height="64" alt="">
          <div class="usa-media-block__body">
            <h3 class="usa-graphic-list__heading">Empower our youth</h3>
            <p>Make the Town's government more accessible to the 18.6% of Town residents below the age of 18. After all, local policy decisions will directly affect their futures.</p>
          </div>
        </div>
      </div>
    </div>
  </section>
  
  <h2>Principled, open-minded leadership</h2>

  <section class="usa-graphic-list usa-section">
    <div class="grid-container">
      <div class="usa-graphic-list__row grid-row grid-gap">
        <div class="usa-media-block tablet:grid-col">
          <img class="usa-media-block__img"  src="/img/icons/black-lives-matter.png" width="64" height="64" alt="">
          <div class="usa-media-block__body">
            <h3 class="usa-graphic-list__heading">Racial justice</h3>
            <p>Use a racial equity framework that clearly names Brookline's history in creating and maintaining racial inequalities. Furthermore, we must acknowledge and provide restitution for the <a href="https://www.bostonglobe.com/2021/10/05/metro/brookline-town-meeting-approves-11-million-settle-racial-discrimination-lawsuit/" class="usa-link usa-link--external">Town's racist actions</a> and history.</p>
          </div>
        </div>
        <div class="usa-media-block tablet:grid-col">
          <img class="usa-media-block__img"  src="/img/icons/politician.png" width="64" height="64" alt="">
          <div class="usa-media-block__body">
            <h3 class="usa-graphic-list__heading">Gender bias</h3>
            <p>Ensure women, as well as non-binary and genderfluid individuals, have representation in all aspects of Town government.</p>
          </div>
        </div>
      </div>
      <div class="usa-graphic-list__row grid-row grid-gap">
        <div class="usa-media-block tablet:grid-col">
          <img class="usa-media-block__img"  src="/img/icons/rgb.png" width="64" height="64" alt="">
          <div class="usa-media-block__body">
            <h3 class="usa-graphic-list__heading">Intersectionality</h3>
            <p>Pursue measures that reflect the interconnected nature of <a href="https://static1.squarespace.com/static/5b2920ad5b409b6a11fdc538/t/621543b7975c7a66fcb794db/1645560781886/BCF_ARPA+Community+Engagement+Report_February+2022.pdf" class="usa-link usa-link--external">social and economic inequality</a>, systems, and justice.</p>
          </div>
        </div>
        <div class="usa-media-block tablet:grid-col">
          <img class="usa-media-block__img"  src="/img/icons/world-pride-day.png" width="64" height="64" alt="">
          <div class="usa-media-block__body">
            <h3 class="usa-graphic-list__heading">LGBTQIA+ liberation</h3>
            <p>Advocate for policies, education and actions that combat heteronormativity. Promote healthy perspectives regarding sex, gender identity, and sexuality.</p>
          </div>
        </div>
      </div>
      <div class="usa-graphic-list__row grid-row grid-gap">
        <div class="usa-media-block tablet:grid-col">
          <img class="usa-media-block__img"  src="/img/icons/birth-control.png" width="64" height="64" alt="">
          <div class="usa-media-block__body">
            <h3 class="usa-graphic-list__heading">Reproductive justice</h3>
            <p>Support unconstrained access to abortion care. Additionally, we must dismantle the additional barriers that people of color and low-income individuals face to contraception access.</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <h2>Good governance</h2>

  <section class="usa-graphic-list usa-section">
    <div class="grid-container">
      <div class="usa-graphic-list__row grid-row grid-gap">
        <div class="usa-media-block tablet:grid-col">
          <img class="usa-media-block__img"  src="/img/icons/online-meeting.png" width="64" height="64" alt="">
          <div class="usa-media-block__body">
            <h3 class="usa-graphic-list__heading">Inclusivity</h3>
            <p>Adopt hybrid (in person and virtual) meeting options, and ensure residents have the technology for virtual access to meetings.</p>
          </div>
        </div>
        <div class="usa-media-block tablet:grid-col">
          <img class="usa-media-block__img"  src="/img/icons/accessibility.png" width="64" height="64" alt="">
          <div class="usa-media-block__body">
            <h3 class="usa-graphic-list__heading">Accessibility</h3>
            <p>Address the interests, concerns, and needs of those with physical, mental, and developmental disabilities or who have limited English proficiency.</p>
          </div>
        </div>
      </div>
      <div class="usa-graphic-list__row grid-row grid-gap">
        <div class="usa-media-block tablet:grid-col">
          <img class="usa-media-block__img"  src="/img/icons/budget.png" width="64" height="64" alt="">
          <div class="usa-media-block__body">
            <h3 class="usa-graphic-list__heading">Representative</h3>
            <p>Push for Town budgets that better reflect our Town's progressive principles and priorities.</p>
          </div>
        </div>
        <div class="usa-media-block tablet:grid-col">
          <img class="usa-media-block__img"  src="/img/icons/unity.png" width="64" height="64" alt="">
          <div class="usa-media-block__body">
            <h3 class="usa-graphic-list__heading">Empower the unrepresented</h3>
            <p>Center the voices of people closest to the issues. Make space for individuals from typically under-represented communities to not only have a seat at the table — but become leaders.</p>
          </div>
        </div>
      </div>
    </div>
  </section>

</div>

<div class="grid-container">
  <Accordion
    items={items}
  />
</div>

<style>
  .usa-media-block__img {
    padding: 0.75rem;
    clip-path: circle(50%);
  }

  .usa-graphic-list:nth-of-type(1) .usa-media-block__img {
    background: #e4a4ff;
    background-color: #f6b4ff66;
  }

  .usa-graphic-list:nth-of-type(2) .usa-media-block__img {
    background: #40dcd6;
    background-color: #57eee766;
  }

  .usa-graphic-list:nth-of-type(3) .usa-media-block__img {
    background: #a7d60a;
    background-color: #b8e72b66;
  }

  .usa-graphic-list:nth-of-type(4) .usa-media-block__img {
    background: #eac200;
    background-color: #fcd20066;
  }



  h2 {
    font-size: 1.5rem;
  }

  .usa-graphic-list {
    background-color: white;
    padding-top: 2rem;
    padding-bottom: 0;
  }

  .usa-graphic-list h3 {
    font-size: 1rem;
  }

  .usa-graphic-list p {
    margin: 0.5rem 0;
  }

  .usa-graphic-list .usa-graphic-list__row .usa-media-block {
    margin-bottom: 2rem;
  }
</style>
