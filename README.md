# stmfork

Proof of concept for migrating the live website **https://stabatmater.info/** to **Hugo + GitHub Pages**.

The goal of this repository is to show how the original Stabat Mater website could run as a static site on GitHub Pages while preserving:

- the structure of the site
- the visual feel of the site
- the existing page types
- the content of migrated pages
- maintainability, so that one source item does not need to be edited in multiple places

## Original website

Source website:

- **https://stabatmater.info/**

This repository is a migration proof of concept for that site, not a redesign and not a reinterpretation.

## What this project should demonstrate

This POC should prove that the original site can be represented in Hugo with:

- a working homepage
- composer overview pages
- composer detail pages with recording data and tables
- texts pages
- translations pages
- blog overview and blog post pages
- about / contact pages
- navigation with dropdown behavior
- derived listing pages such as country / period / duration views

## Key migration principle

This repository is a migration proof of concept, not a content rewrite.

If a page from the live site is migrated into this repository, its content should remain **identical to the source page**.

That means:

- do **not** paraphrase migrated text
- do **not** summarize migrated text
- do **not** regenerate migrated page copy with an LLM
- do **not** replace missing source text with invented filler

If a page differs materially from the original, it should be treated as **not yet migrated**.

## Desired maintenance model

A major reason for doing this POC is maintainability.

The site should be structured so that adding or editing one source item automatically updates the derived views that depend on it.

Examples:

- adding a composer should automatically update:
  - the composer detail page
  - the composers overview
  - country listings
  - period listings
  - duration-based listings
- adding a blog post should automatically update:
  - the post page
  - the blog overview
  - recent-post lists

The goal is to avoid editing the same information manually in multiple places.

## GitHub Pages target

This repository is published as a GitHub Pages **project site** under:

- **https://aistars26.github.io/stmfork/**

So internal links, assets, and navigation must work correctly under the `/stmfork/` base path.

## Current scope of the POC

This repository already contains examples of:

- home page
- composers overview
- composer detail pages
- texts overview and detail pages
- translations overview and detail pages
- blog overview and blog post page
- about page
- contact page
- taxonomy / derived pages
- GitHub Pages deployment via GitHub Actions

## Workflow for future fidelity work

When continuing the migration work:

1. choose a page that already exists in the POC
2. compare it against the corresponding page on **https://stabatmater.info/**
3. correct the POC until the migrated content and structure match
4. verify in the browser
5. verify a second way (for example via raw HTML/text comparison)
6. only then consider that page done

## Local development

If Hugo is installed:

```bash
hugo server
```

## Deploy

A push to `main` triggers GitHub Actions to build and publish the site to GitHub Pages.
