<script context="module">
  export const prerender = false;

  let faq = [{
    question: "Can I join BEC?",
    answer: `You sure can! Here is <a href="https://docs.google.com/forms/d/e/1FAIpQLSd8oUbsHFUKdJgj2NmD-bH2tFztGdXuXxcC3zXfxqrvDip1ig/viewform" class="usa-link usa-link--external">our onboarding form</a>.`
  }, {
    question: "What is Town Meeting?",
    answer: "Town Meeting is the 255-person assembly of elected representatives who decide the legislative policies of Brookline. Each year during the Town's May municipal election at least a third of each precinct's Town Meeting seats (5 positions) are on the ballot."
  }, {
    question: "Who are my Town Meeting members? Which precinct am I in?",
    answer: `<p>Your precinct determines who your Town Meeting members are. As of re-precincting last year (following the latest census), <a href="https://www.brooklinema.gov/DocumentCenter/View/26965/Brookline-Precinct-Map-2022" class="usa-link usa-link--external">Brookline has 17 precincts</a>. You can use the MA Secretary of State's website to <a href="https://www.sec.state.ma.us/WhereDoIVoteMA/WhereDoIVote" class="usa-link usa-link--external">look up your precinct and polling place</a>.</p>
      <p>Once you know your precinct, you can cross reference that number with who this <a href="https://www.brooklinema.gov/DocumentCenter/View/6574" class="usa-link usa-link--external">spreadsheet from the Town [downloads file]</a> lists as your fifteen Town Meeting members.</p>`
  }, {
    question: `What is the <a href="https://www.brooklinema.gov/343/Select-Board" class="usa-link usa-link--external">Select Board</a>?`,
    answer: `The town's five-person chief executive body. Each Select Board member is elected by a Town-wide ballot for three year terms. The series is: two seats are up one year; the next year, two different seats are up; the third year, the fifth seat is up; and then the cycle repeats.`
  }, {
    question: "When are the next elections?",
    answer: `On Tuesday, September 6th <a href="https://www.raulforrep.com/" class="usa-link usa-link--external">Raul Fernandez</a> — who is running to be the State Representative for the 15th Norfolk district — will be on the ballot. There is an election again on Tuesday, November 8th. And the next municipal election will be in May 2023.`
  }, {
    question: "Where can I register to vote?",
    answer: `<a href="https://www.sec.state.ma.us/OVR" class="usa-link usa-link--external">Register to vote</a> on the Massachusetts Secretary of State's website.`
  }, {
    question: "What is charter change?",
    answer: `Each municipality has a charter that outlines its local government's powers, functions, fundamental workings, and organization. Should Brookline want to write for itself a new charter — for example, so as to adopt city-style governance — <a href="https://www.mma.org/resource/how-to-go-about-a-charter-change/" class="usa-link usa-link--external">charter change processes exist</a>. Massachusetts state law allows for either an elected charter commission or an appointed charter committee; see the link above for more details on each approach.`
  }]
</script>

<svelte:head>
  <title>FAQ — Brookline Equity Coalition</title>
  <meta name="description" content="Frequently asked questions about Brookline Equity Coalition.">
</svelte:head>

<!--
  This is purposely not in the head because there's a bug that
  causes it to duplicate:
  https://github.com/sveltejs/svelte/issues/7444
-->
{@html `<script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "FAQPage",
    "mainEntity":
      ${JSON.stringify(faq.map((item) => {
        return {
          "@type": "Question",
          "name": item.question,
          "acceptedAnswer": {
            "@type": "Answer",
            "text": item.answer
          }
        }
      }))}
  }
</script>`}

<section class="usa-section grid-container usa-prose">
  <div class="grid-row grid-gap">
    <div class="tablet:grid-col-4">
      <h1 class="margin-top-0">Frequently asked questions</h1>
    </div>
    <div class="tablet:grid-col-8">
      <dl>
        {#each faq as item}
          <dt>{@html item.question}</dt>
          <dd>{@html item.answer}</dd>
        {/each}
      </dl>
    </div>

</section>

<style>
  dt {
    margin-top: 1rem;
    font-weight: 600;
  }

  dd > p {
    margin-top: 0;
  }
</style>