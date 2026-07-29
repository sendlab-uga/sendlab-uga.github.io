# SEND Lab website & manual

Source for the SEND Lab's public website and internal lab manual, built with
[Jekyll](https://jekyllrb.com/) and hosted on [GitHub
Pages](https://pages.github.com/).

## Setup (one-time)

1. Create a GitHub organization for the lab (e.g. `SEND-Lab-UGA`) at
   https://github.com/organizations/new — free plan.
2. Create a repo inside that org named **exactly** `<org-name>.github.io`
   (e.g. `send-lab-uga.github.io`) — this naming convention is what makes
   GitHub auto-publish it.
3. Push the contents of this folder to that repo's `main` branch.
4. In the repo's **Settings → Pages**, confirm the source is set to the
   `main` branch, root folder. GitHub builds and publishes automatically —
   no separate build step needed for a standard Jekyll site.
5. Update `_config.yml`: set `url` to your actual Pages URL, and update
   `email`.
6. Add lab members as **org members** (Settings → People → Invite member) so
   they can open pull requests to edit their own bio pages, add
   publications, etc.

## Structure

```
_config.yml          site settings, nav, branding
index.md              homepage
research.md           research overview
people.md             team overview (links to members/)
publications.md       publications list
join.md                "join the lab" page
members/               one file per person (start from _template.md)
_manual/               the lab manual, one file per section (collection)
_layouts/              page templates
assets/css/style.scss  branding (hunter green #06402B, Calibri)
```

## Editing

- Small edits (fixing a typo, updating a bio): edit the file directly on
  github.com and commit — no local setup needed.
- Bigger changes: clone locally, run `bundle exec jekyll serve` to preview
  at `localhost:4000`, then push and open a pull request.

## Adding a new manual section

Add a new `.md` file to `_manual/` with frontmatter:

```yaml
---
title: Your section title
order: 7
---
```

Then add a link to it in `_manual/index.md`.

## Adding a new lab member

Copy `members/_template.md` to `members/firstname-lastname.md`, fill in the
frontmatter and a short bio, and link them from `people.md`.
