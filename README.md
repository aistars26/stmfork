# stmfork

Proof of concept for migrating the Stabat Mater website to **Hugo + GitHub Pages**.

This repository is intended to demonstrate how the original website structure and look-and-feel could work in a static Pages-based setup.

## Current goals

- preserve the visual identity as much as possible
- demonstrate all important page types
- avoid depending on the live production site for navigation or page content
- use GitHub Actions to build and publish the site automatically

## Included page types

- home page
- composers overview
- composer detail page
- blog overview
- blog post page
- texts overview and detail pages
- translations overview and detail pages
- about page
- contact page

## Run locally

```bash
hugo server
```

## Deploy

A push to `main` triggers GitHub Actions to build and publish the site to GitHub Pages.
