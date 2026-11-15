# Bridge2Learn

Bridge2Learn is a static Astro site. The production build is written to `dist/`.

## Run locally

Use Node.js 24.19.0 (the version pinned in `netlify.toml` and GitHub Actions) and npm:

```sh
npm ci
npm run dev
```

Create and preview a production build:

```sh
npm run build
npm run preview
```

`package-lock.json` is committed so clean installs use the locked dependency versions. Do not upload `node_modules/` or `dist/`; they are generated and ignored by Git.

## Deploy with GitHub and Netlify

1. Push the project root—including `package.json`, `package-lock.json`, `netlify.toml`, `src/`, and `public/`—to a GitHub repository.
2. In Netlify, import that repository and select the production branch.
3. Netlify reads `netlify.toml`: it installs dependencies, runs `npm run build`, and publishes `dist/`.
4. Pushes to the production branch trigger a new deploy. Pull requests also run the GitHub Actions build check.

The GitHub Actions workflow uses the same Node version and locked install as the local setup. No Netlify adapter is needed for this statically generated site.
