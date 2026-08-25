# OWASP San Fernando Valley

This repository holds the source files for the OWASP San Fernando Valley chapter page.

**Live page: <https://sfv.owasp.org/>**

If you came here looking for meeting information, read the live page instead.

## Who we are

OWASP San Fernando Valley is the local OWASP chapter for the San Fernando Valley and the
surrounding parts of greater Los Angeles. The chapter is for developers, security
engineers, QA and test professionals, students, and anyone else who builds or runs
software.

Meetings are free and anyone can attend. You do not need to be an OWASP member, and you
do not need a security background.

The chapter is relaunching in 2026 after several dormant years. We have not set meeting
dates yet, we do not have a venue, and OWASP is still setting up our Meetup group. The
live page has the latest.

- Chapter page: <https://sfv.owasp.org/>
- LinkedIn: <https://www.linkedin.com/company/owasp-sfv>
- YouTube: <https://www.youtube.com/@OWASPSanFernandoValley>
- Sibling chapter, OWASP Los Angeles: <https://owasp.org/www-chapter-los-angeles/>

## Why this repo exists

owasp.org runs on Jekyll. Every OWASP chapter, project, and committee keeps its own
repository under the OWASP GitHub organization, and GitHub Pages publishes each one to its
own path on owasp.org. There are roughly 600 chapter repos.

This chapter is one of the few with its own subdomain. The `CNAME` file makes GitHub
Pages serve the site at <https://sfv.owasp.org/>, and the OWASP Foundation holds the
matching DNS record in the `owasp.org` zone. The old path,
`https://owasp.org/www-chapter-san-fernando-valley/`, redirects there, so older links
still work.

Repository names follow a fixed pattern: `www-chapter-<name>` for chapters,
`www-project-<name>` for projects, `www-committee-<name>` for committees.

## What is in here

| File | What it does |
|---|---|
| `index.md` | The chapter page body. Its front matter tells owasp.org our region, state, and postal code |
| `leaders.md` | The leader list. The theme renders it into the right sidebar |
| `info.md` | Sidebar content above the leaders. Chapter news and social links |
| `chapter.owasp.yaml` | Chapter metadata for the [OWASP Nest](https://owasp.org/www-project-nest/) directory. Validate against the [Nest schema](https://github.com/OWASP/nest-schema) before changing it |
| `_config.yml` | Jekyll config. Points at the shared OWASP theme |
| `CNAME` | The custom domain, `sfv.owasp.org`. OWASP staff added it and OWASP owns the matching DNS record. Do not edit or delete it |
| `404.html` | Not-found page |
| `Gemfile` | Ruby dependencies for building locally |
| `assets/images/` | Images the page uses |

## How the page is built

GitHub Pages rebuilds the site whenever a commit lands on `master`. Nobody runs a deploy
step or triggers a build by hand. Give it a few minutes after a push.

The layout, header, footer, and sidebar come from the shared theme at
[OWASP/www--site-theme](https://github.com/OWASP/www--site-theme), which `_config.yml`
selects through `remote_theme`. We do not control that theme. When OWASP changes it, every
OWASP page changes at once.

To preview locally:

```sh
bundle install
bundle exec jekyll serve
```

Jekyll writes the result into a `_site/` folder. That folder is build output. Do not
commit it.

## Editing notes

**`leaders.md` and `info.md` must have no YAML front matter.** The theme finds them in
Jekyll's static file list, and a `---` block drops a file from that list, taking its whole
sidebar section with it. Jekyll reports no error.

**The Participation section of `index.md` is shared boilerplate.** Hundreds of chapter
repos carry the same text. Leave the wording alone so ours matches the rest of OWASP.

**Links to files in this repo start with `/`, which depends on the `CNAME` file.** The site
root is `sfv.owasp.org` only while that file exists. Delete it and every such link breaks
at once, again with no error from Jekyll.

## Contributing

Corrections are welcome. Open an issue or send a pull request.

For anything about running the chapter, speaking at a meeting, hosting one, or sponsoring,
contact a chapter leader directly. The live page lists them. Do not open an issue here for
those.

To speak at this or any OWASP chapter, read the
[speaker agreement](https://policy.owasp.org/legal/speaker-agreement) first.

## What does not belong here

This repository is public and it is the chapter's website. Keep out:

- Attendee lists, sign-in sheets, registration exports, or anything else that identifies
  people. OWASP's privacy rules and GDPR apply, and we must not share attendee data
  without informed opt-in.
- Credentials of any kind.
- Build output such as `_site/`.

## About OWASP

The Open Worldwide Application Security Project (OWASP) is a nonprofit foundation that
works to improve the security of software. Anyone can use its projects, tools, documents,
forums, and chapters for free.

Chapters run under the
[OWASP Chapters Policy](https://policy.owasp.org/operational/chapters).

This link sends your donation to our chapter rather than to the Foundation's general fund:

<https://owasp.org/donate?reponame=www-chapter-san-fernando-valley&title=OWASP+San+Fernando+Valley>
