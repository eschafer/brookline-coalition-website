<script context="module">
	export const prerender = true;
</script>

<script>
	import { page } from '$app/stores';
  import Header from '$lib/uswds/Header.svelte';
  import Footer from '$lib/uswds/Footer.svelte';

  let data = {
    header: {
      title: 'Brookline Equity Coalition',
      logo: {
        src: "/img/coalition/logo.svg",
        alt: "Home",
      },
      links: [
        {
          href: "/",
          label: "Home",
        },
        {
          href: "/about",
          label: "About",
        },
        {
          href: "/endorsements",
          label: "Endorsements",
        },
        {
          href: "/voter-guide",
          label: "Voter Guide",
        },
        {
          href: "/get-involved",
          label: "Get Involved",
        },
      ],
    },
    footer: {
      links: [
        {
          href: "/",
          label: "Home",
        },
        {
          href: "/about",
          label: "About",
        },
        {
          href: "/endorsements",
          label: "Endorsements",
        },
        {
          href: "/voter-guide",
          label: "Voter Guide",
        },
        {
          href: "/get-involved",
          label: "Get Involved",
        },
      ],
    }
  }
</script>

<svelte:head>
	<link rel="alternate" href={`https://www.example.org${$page.url.pathname.replace(/^\/(es|zh)($|\/)/, '/')}`} hreflang="en" />
	<link rel="alternate" href={`https://www.example.org/es${$page.url.pathname.replace(/^\/(es|zh)($|\/)/, '/')}`} hreflang="es" />
	<link rel="alternate" href={`https://www.example.org/zh${$page.url.pathname.replace(/^\/(es|zh)($|\/)/, '/')}`} hreflang="zh" />
	<link rel="alternate" href={`https://www.example.org${$page.url.pathname.replace(/^\/(es|zh)($|\/)/, '/')}`} hreflang="x-default" />
</svelte:head>

<div class="wrapper">

  <nav aria-label="Skip Link and Language Selector" class="controls">
    <ul>
      <li>
        <a class="usa-skipnav" href="#main-content">Skip to main content</a>
      </li>
      <li>
        <a href={`http://${$page.host}${$page.url.pathname.replace(/^\/(es|zh)($|\/)/, '/')}`}>English</a>
      </li>
      <li>
        <a href={`http://${$page.host}/es${$page.url.pathname.replace(/^\/(es|zh)($|\/)/, '/')}`}>Español</a>
      </li>
      <li>
        <a href={`http://${$page.host}/zh${$page.url.pathname.replace(/^\/(es|zh)($|\/)/, '/')}`}>中文</a>
      </li>
    </ul>
  </nav>

  <Header
    title={data.header.title}
    logo={data.header.logo}
    links={data.header.links}
  />


  <main id="main-content">
    <slot></slot>
  </main>


  <Footer
    links={data.footer.links}
  />
</div>

<style>
  .wrapper {
    display: grid;
    grid-template-rows: min-content min-content 1fr;
    background-color: #fcf9f6;
  }

  
  .controls > ul {
    margin: 0;
    padding: 0 1rem;
    display: flex;
    justify-content: flex-end;
    background: #2700B3;
    border-bottom: 8px solid;
    border-bottom: 4px solid #d43d7c;
    border-image: linear-gradient(to left, #FFD500, #A4D301, #0EC4BE) 1;
  }

  .controls > ul > li {
    display: inline-block;
    padding: 0.5rem 0.5rem;
    list-style: none;
    font-size: 0.875rem;
  }

  .controls > ul > li:last-child {
    padding-right: 0;
  }

  .controls > ul > li:not(li:first-child) > a {
    color: #fffb;
  }


  .usa-footer__primary-section {
    background-color: #00656D;
  }

  .usa-footer__primary-link, .usa-footer__contact-info a {
    color: #ffffff;
  }

  .usa-footer__secondary-section {
    background-color: #00363B;
    color: #ffffff;
  }
</style>