# nodewave-ea

Production-ready Vue 3 application with SEO, structured data, and performance tooling for NodeWave.net.

## Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur).

## Environment Configuration

Create a `.env` file (or use deployment secrets) with the following keys to enable analytics and supporting pixels. In development these integrations remain disabled unless `VITE_ENABLE_ANALYTICS=true` is set.

```ini
VITE_GA_MEASUREMENT_ID=G-XXXXXXXXXX
VITE_FB_PIXEL_ID=000000000000000
VITE_HOTJAR_ID=0000000
VITE_ENABLE_ANALYTICS=false
VITE_ENABLE_HOTJAR=false
```

## SEO & Performance Tooling

- `npm run seo:validate` &mdash; run pre-deploy SEO validation checks.
- `npm run seo:generate-sitemap` &mdash; rebuild `public/sitemap.xml` from the dynamic route list.
- `npm run seo:audit` &mdash; execute validation followed by sitemap regeneration.
- Core Web Vitals optimisations (lazy loading, CLS guards, structured data) are wired through `src/composables/useSEO.js` and `src/utils/performanceUtils.js`.

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```

### Run Unit Tests with [Vitest](https://vitest.dev/)

```sh
npm run test:unit
```

### Run End-to-End Tests with [Playwright](https://playwright.dev)

```sh
# Install browsers for the first run
npx playwright install

# When testing on CI, must build the project first
npm run build

# Runs the end-to-end tests
npm run test:e2e
# Runs the tests only on Chromium
npm run test:e2e -- --project=chromium
# Runs the tests of a specific file
npm run test:e2e -- tests/example.spec.ts
# Runs the tests in debug mode
npm run test:e2e -- --debug
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```
