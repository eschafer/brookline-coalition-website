<script>
	import { onDestroy, onMount } from 'svelte';
	import { page } from '$app/stores';

	export let title;
  export let logo;
  export let links;

	let accordion;
	let navigation;

	onMount(async () => {
		accordion = await import('uswds/src/js/components/accordion');
		navigation = await import('uswds/src/js/components/navigation');
    
		accordion.on();	
		navigation.on();
  });

  onDestroy(async() => {
    if (accordion) {
      accordion.off();
    }
		if (navigation) {
			navigation.off();
		}
  })
</script>

<header class="usa-header usa-header--basic">
  <div class="usa-nav-container">
    <div class="usa-navbar">

      <!-- title/logo -->
      <div class="usa-logo" id="basic-logo">
        <em class="usa-logo__text">
          <a href="/">
            {#if logo}
							<img src={logo.src} role="img" alt={logo.alt} class="usa-logo-img" />
						{:else}
							{title}
						{/if}
          </a>
        </em>
      </div>

      <!-- small screen menu button -->
      <button class="usa-menu-btn">Menu</button>

    </div>

    <!-- nav links -->
    <nav aria-label="Primary navigation" class="usa-nav">

      <!-- small screen close button -->
      <button class="usa-nav__close">
        <img src="/img/usa-icons/close.svg" role="img" alt="Close" />
      </button>

      {#if links}
        <ul class="usa-nav__primary usa-accordion">
          {#each links as link}
            <li class="usa-nav__primary-item">
              {#if link.links}
                <button
                  class="usa-accordion__button usa-nav__link"
                  aria-expanded="false"
                  aria-controls="basic-nav-section-one"
                >
                  <span>{link.label}</span>
                </button>

                <ul id="basic-nav-section-one" class="usa-nav__submenu">
                  {#each link.links as sublink}
                    <li class="usa-nav__submenu-item">
                      <a href={sublink.href}>{sublink.label}</a>
                    </li>
                  {/each}
                </ul>
              {:else}
                <a
                  href={link.href}
                  class="usa-nav__link"
                  class:usa-current={$page.url.pathname === link.href}
                >
                  <span>{link.label}</span>
                </a>
              {/if}
            </li>
          {/each}
        </ul>
      {/if}
    </nav>
  </div>
</header>

<style>
  .usa-navbar {
    height: auto;
  }

  .usa-logo a {
    padding: 1rem 1rem 1rem 0;
  }

  .usa-logo__text > a:nth-child(1) {
    display: inline-block;
  }

  .usa-logo-img {
    max-height: 6rem;
  }

  .usa-menu-btn {
    align-self: flex-start;
  }

  @media (min-width: 20em) {
    .usa-header--basic .usa-nav-container {
      flex-wrap: wrap;
    }
    .usa-header--basic .usa-navbar {
      width: auto;
    }
    .usa-header--basic .usa-nav {
      width: auto;
    }

    .usa-nav-container::after {
      content: none;
    }

    .usa-nav__primary {
      flex-wrap: wrap;
    }
  }

  @media (min-width: 30em) {
    .usa-logo a {
      padding: 0;
    }

    .usa-nav__primary {
      margin-left: -1rem;
      margin-right: -1rem;
    }
  }
</style>
