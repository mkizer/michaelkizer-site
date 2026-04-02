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

---

## Deploying Your Astro Site to Cloudflare Pages

Now that your site is fully built statically and working smoothly locally, deploying to Cloudflare Pages is extremely straightforward! By following these steps, you will utilize continuous deployment—meaning any time you push new code or draft a new post, Cloudflare will automatically rebuild and host your site.

### Step 1: Push Your Project to GitHub (or GitLab/Bitbucket)
If you haven't already, you need to push your local repository to a remote Git provider like GitHub. Cloudflare accesses your repository to build the source code automatically.

1. Create a new repository on your GitHub account.
2. In your local terminal, commit any existing changes:
   ```bash
   git add .
   git commit -m "Initial commit of Astro site conversion"
   ```
3. Push the main branch to your remote repository:
   ```bash
   git remote add origin https://github.com/your-username/your-repo-name.git
   git branch -M main
   git push -u origin main
   ```

### Step 2: Connect to Cloudflare Pages
Now that your code lives on GitHub, you can link it to Cloudflare.

1. Log in to the [Cloudflare Dashboard](https://dash.cloudflare.com/).
2. In the left-hand navigation menu or main dashboard menu, click on **Workers & Pages**.
3. Click the **Create Application** button, and then navigate to the **Pages** tab.
4. Select **Connect to Git**.
5. Log in with your GitHub account, grant Cloudflare access (either to all repositories or just this specific one), and select your newly created repository from the list. Choose **Begin setup**.

### Step 3: Configure Build Settings
You will now configure how Cloudflare builds your Astro application.

1. **Project Name**: This will be used for your initial `.pages.dev` subdomain (e.g., `michaelkizer-site.pages.dev`). You can set up your custom domain `riverwideoceandeep.com` afterward.
2. **Production Branch**: Keep this as `main` (or whichever branch you are using).
3. **Framework Preset**: In the dropdown, select **None** (Do *not* select Astro!).
    - Since you are deploying a pure Static Site Generation (SSG) app, selecting the "Astro" preset causes Cloudflare to incorrectly force-install the `@astrojs/cloudflare` server-side rendering adapter, breaking your build. Selecting **None** avoids this.
    - **Build Command**: Type `npm run build`
    - **Output Directory**: Type `dist`

> [!CAUTION] 
> Do **not** try to configure or add the `@astrojs/cloudflare` server adapter in your `astro.config.ts`. As we discussed before, to keep your images linking properly without breaking, your project should build as a **Standard Static Site (SSG)** which is exactly what your current code achieves natively. Simply having Astro output static HTML files to `dist/` is the correct path!

### Step 4: Add Critical Environment Variables
Modern tools like Astro 6 and your underlying Vite dependency strongly prefer newer Node versions to process everything smoothly. Before you click "Save and Deploy", let's make sure Cloudflare uses a modern version of Node. 

1. Expand the **Environment Variables (Advanced)** section.
2. Add a new variable:
   - **Variable name**: `NODE_VERSION`
   - **Value**: `22.16.0` *(or any modern Node 22.x string)*
3. Add any other `.env` variables if you have them (such as your `PUBLIC_GOOGLE_SITE_VERIFICATION` token if you use that feature).

### Step 5: Save and Deploy!
1. Click **Save and Deploy**. Cloudflare will grab your codebase, provision a build environment installing your dependencies using Node 20, and run `npm run build`.
2. Within 2-3 minutes, your live site will be given a secure `.pages.dev` link.

### Step 6: Setup Your Custom Domain
To bring your site full circle and utilize your own domain:
1. From your new project's Cloudflare Pages dashboard, go to the **Custom Domains** tab.
2. Click **Set up a custom domain**.
3. Type in your domain (`riverwideoceandeep.com` or `michaelkizer.com`, whichever is your preference).
4. Cloudflare will automatically update the DNS CNAME records for you since your DNS is actively managed by them. Your site shouldn't have any downtime!
