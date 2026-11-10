# thefederation.eu

The website of the European Federation of Churches of Christ, built with [Zola](https://www.getzola.org/).

- `content/`: the pages, as Markdown files with TOML front matter
- `static/media/`: pictures and downloadable files
- `static/admin/`: the [Sveltia CMS](https://sveltiacms.app/) editor and its configuration (`config.yml`)
- `themes/efcc/`: the theme (templates and stylesheet)

## Editing the content
Go to `/admin/` on the website and choose *Sign In Using Access Token*, with a GitHub
[fine-grained token](https://github.com/settings/personal-access-tokens) that has *Contents: Read and write*
access to this repository. Saving an entry commits to `main`; the server rebuilds the site within 5 minutes
(see `efcc/website.nix` in [nixos-config](https://github.com/the-efcc/nixos-config)).

Lists of churches, projects and tools are built from the files of their folder:
- `extra.image` is the teaser picture, `extra.banner` the picture behind the page title.
- `extra.status` (projects) is the registration status: `to come`, `open`, `last call` or `closed`.
- `extra.link` makes the list entry point to another website, e.g. the event's registration page.
- The teaser text is what comes before a `<!-- more -->` line.

## Working on the site
```bash
nix shell nixpkgs#zola -c zola serve
```
