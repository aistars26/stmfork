# stmfork

Proof of concept for migrating the Stabat Mater website to **Hugo + GitHub Pages**.

This repo is not meant to be a loose reinterpretation of the live site. The goal is to prove that the current WordPress site can be represented faithfully in a static Hugo + GitHub Pages setup.

## What this project is trying to prove

- the main page types can exist as static Hugo content
- navigation can work on a GitHub Pages project site
- derived pages can be generated from source content instead of being maintained manually in multiple places
- migrated pages can match the live source site **literally**, not just approximately

## Non-negotiable content rule

For pages that are considered "migrated" in this proof of concept:

- **Do not paraphrase** source text
- **Do not summarize** source text
- **Do not regenerate** source text with an LLM
- **Do not invent marketing copy** to fill gaps

If content is taken over from the live site, it should be copied **literally** as far as practical.
If a page is not yet faithfully migrated, treat it as incomplete rather than "good enough".

## Current state

The repo already contains working Hugo page types for:

- home page
- composers overview
- composer detail page(s)
- blog overview
- blog post page
- texts overview and detail page(s)
- translations overview and detail page(s)
- about page
- contact page
- taxonomy-style pages such as countries / periods
- a duration-based composers view

GitHub Pages is configured and deploys from `main`.

## Important warning for the next session

This repo has already gone through several partial fidelity passes. Some structure, navigation, dropdowns, taxonomy pages, local asset copies, and GitHub Pages path fixes are in place.

However, **do not assume the migrated pages are yet fully source-identical**.

There were earlier mistakes where content was paraphrased or rewritten instead of being copied literally. Future work should therefore start from verification, not trust.

## Required workflow for future fidelity work

When continuing this migration, use this process:

1. Pick a page that currently exists in the POC
2. Fetch/open the corresponding live page from `stabatmater.info`
3. Compare the source page and the POC page **literally**
4. Fix the POC page until the migrated content matches
5. Verify the rendered result in the browser
6. Perform a second verification path (for example raw HTML/text comparison)
7. Only then mark that page as done

Do this **page by page**.

## Pages / areas explicitly known to need verification

Even if they look close, they must still be treated as suspect until checked literally:

- home page
- about page
- contact page
- texts pages, especially the Latin text page
- translations pages
- blog overview / blog detail
- composer pages, including large recording sections and tables
- taxonomy / derived list pages
- navigation chrome / footer / sidebar blocks

## Maintenance model target

A key goal of this repo is that adding one content item should update all relevant derived pages automatically.

Examples:

- adding a composer should automatically affect:
  - composer detail
  - composers overview
  - country listing
  - period listing
  - duration listing
- adding a blog post should automatically affect:
  - blog detail
  - blog overview
  - recent posts widgets

If something still requires manual duplication across multiple pages, treat that as incomplete design.

## Internal links / GitHub Pages constraint

This repo is published as a **GitHub Pages project site** under:

- `https://aistars26.github.io/stmfork/`

So internal links must be safe for a project-site base path.
Avoid root-relative links that escape `/stmfork/`.

## Run locally

If Hugo is available locally:

```bash
hugo server
```

If Hugo is not installed on the machine, install or download a local binary before doing render verification.

## Deploy

A push to `main` triggers GitHub Actions to build and publish the site to GitHub Pages.

## Practical expectation for the next session

Do not report "done" unless the currently migrated pages have been:

- checked one by one
- compared literally with the live source
- browser-verified
- verified a second way

If there is any doubt, say it is **not done yet**.
