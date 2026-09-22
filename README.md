# barakahtechzone.github.io

**This repository is generated. Do not edit it by hand — your changes will be
overwritten on the next deploy.**

It holds the built static export of the Barakah Tech Zone website, published to
GitHub Pages at <https://barakahtechzone.github.io>.

## Source of truth

| | |
|---|---|
| Source repository | [barakahtechzone/barakahtechzone](https://github.com/barakahtechzone/barakahtechzone) |
| Workflow | `.github/workflows/deploy-github-pages.yml` |
| Published branch | `main` (force-orphaned on every deploy — one commit, always) |
| Primary domain | <https://barakahtechzone.com> |

To change this site, edit the source repository and push to `main`. The workflow
typechecks, builds the export, asserts all 23 pages are present, and rewrites
this branch.

## A note on the old names

The organisation and both repositories were renamed from `barakah-tech-zone` to
`barakahtechzone`. GitHub redirects the old **git** URLs, so pushes and clones
against `barakah-tech-zone/...` still work and fail silently rather than loudly.

The old **hostname** does not redirect. `https://barakah-tech-zone.github.io`
returns 404; only `https://barakahtechzone.github.io` serves this site. Use the
new name everywhere.

## About the canonical URLs

This deployment is a **canonical mirror**. Its pages declare
`https://barakahtechzone.com/...` as their canonical URL, and its `sitemap.xml`
lists the `.com` URLs. That is intentional: the same content on two hosts would
otherwise compete with itself in search results.

If you want this address to be indexed in its own right, set
`NEXT_PUBLIC_SITE_URL: https://barakahtechzone.github.io` in the workflow and
redeploy.

## Notes

- `.nojekyll` is required — Jekyll would otherwise skip the `_next/` asset
  directory because it begins with an underscore.
- `.gitattributes` sets `* -text`, so `core.autocrlf=true` on Windows cannot
  rewrite all 226 files on checkout and report the tree as modified.
- The export uses `trailingSlash: true`, so every route is a directory
  containing an `index.html`.
- `404.html` at the root is served by GitHub Pages for unknown paths.
