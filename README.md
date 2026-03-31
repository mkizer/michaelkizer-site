# Michael Kizer - Astro Website

This is the repository for Michael Kizer's personal website, migrated from WordPress to a fast, statically-generated site using [Astro v6](https://astro.build/) and the [AstroPaper](https://github.com/satnaing/astro-paper) theme.

## Prerequisites

Before running the project locally, ensure you have the following installed:
- [Node.js](https://nodejs.org/) (v18.17.1 or higher is recommended for Astro v6)
- npm (installed automatically with Node.js)

## Getting Started

To get the project running locally on your machine, follow these steps:

1. **Install Dependencies:**
   Install all the packages required by the project using npm:
   ```bash
   npm install
   ```

2. **Start the Development Server:**
   Launch the local Astro development server:
   ```bash
   npm run dev
   ```
   The site should now be accessible in your browser at `http://localhost:4321`.

## Available Commands

Here are the most common scripts you'll use while working with the project:

- `npm run dev` - Starts the local development server.
- `npm run build` - Builds the site for production into the `dist/` directory.
- `npm run sync` - Synchronizes Astro content collections and generates TypeScript types.
- `npx tsc --noEmit` - Runs the TypeScript compiler to check for type errors without generating files.
- `npm run format` - Formats the codebase using Prettier.

## Key Modifications & Features

This project started from the base AstroPaper theme but has been significantly customized and upgraded:

### 1. Astro v6 Upgrade
The project dependencies (including `@astrojs/rss`, `@astrojs/sitemap`) and structure have been upgraded to Astro v6. 
- **Vite 7**: A resolution override for Vite 7 (`"overrides": { "vite": "^7" }`) was added to `package.json` to ensure compatibility with Astro 6.
- **Top-Level Font Config**: Font configurations were moved out of the legacy `experimental` block to the top-level `fonts` option in `astro.config.ts`.
- **Content Layer API**: Uses Astro 5/6's new Content Layer API, configured via `src/content.config.ts` (loading blog posts from `src/data/blog/`).

### 2. TypeScript Strict Mode
The project is configured to use strict TypeScript checking. Ensure any new files or modifications comply with the `astro/tsconfigs/strict` configuration in `tsconfig.json`.

### 3. Image Zooming (Medium-Zoom)
To replace the default WordPress image behavior, the lightweight `medium-zoom` package was integrated globally via `src/layouts/Layout.astro`. 

**How it works:**
Standard Markdown images are automatically optimized by Astro's asset pipeline, and the client-side script enables seamless zooming when clicked.

**Excluding Images from Zoom:**
If you have a decorative or small image that you do *not* want to scale up, simply add `"no-zoom"` as the image title in your markdown:
```md
<!-- This image will NOT zoom on click -->
![My smaller image](../assets/images/small.png "no-zoom")
```

### 4. Custom Routing & Navigation
A "Portfolio" page (`src/pages/website-portfolio.md`) was created to house the migrated WordPress portfolio, and the global navigation bar (`src/components/Header.astro`) was updated to include a direct link to it.
