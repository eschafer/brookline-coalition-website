# svelte-uswds
 
## File structure

- `build`: build output
- `locales`: translated strings for each locale
- `packages`: uswds gulpfile is in here because it relies on conflicting dependencies compared to root
- `src`
  - `lib`: components
    - `pages`: localized page components
    - `uswds`: uswds components
  - `routes`: actual webpages; use components from `src/lib/pages`
  - `styles`
- `static`: static assets
