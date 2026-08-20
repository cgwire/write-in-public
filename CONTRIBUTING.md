# Contributing

This repository is a blog being written in public.

Hundreds of articles across 10 acts, covering the working life of an animation studio from before it exists to after it's sold. It is published chapter by chapter, in order, and co-authored with the industry. Every article is versioned, credited, and open to correction, including the ones already published.

You do not need to write a whole article to contribute. Most of what makes this blog good will arrive as a corrected number, a war story, a "that's not how it works in Tokyo," or half an hour on a call.

## Table of contents

- [Contributing](#contributing)
  - [Table of contents](#table-of-contents)
  - [Ways to contribute](#ways-to-contribute)
  - [The map](#the-map)
  - [The production timeline](#the-production-timeline)
  - [Repository structure](#repository-structure)
  - [Frontmatter](#frontmatter)
  - [Style Guide](#style-guide)
  - [Evidence, sources and anonymity](#evidence-sources-and-anonymity)
  - [Pull requests](#pull-requests)
  - [Review](#review)
  - [Credit](#credit)
  - [Versioning and changelogs](#versioning-and-changelogs)
  - [Licensing and IP](#licensing-and-ip)
  - [What we don't publish](#what-we-dont-publish)
  - [Code of conduct](#code-of-conduct)
  - [Where to talk](#where-to-talk)

## Ways to contribute

Ordered roughly by commitment:

| Contribution | What it looks like | Where it starts |
|---|---|---|
| **Correction** | A number, a term, a country-specific rule that's wrong | *Suggest an edit* on any article, or open an `article: correction` issue |
| **Testimony** | "Here's what happened when we tried that", quoted or anonymous | `contribution: testimony` issue, or bring it to Discord |
| **Review** | Read a draft in the community round, mark what's wrong or missing | Comment on the open draft PR |
| **Data** | Rates, timelines, headcounts, margins; cf [anonymity](#evidence-sources-and-anonymity) | `contribution: data` issue |
| **Interview** | 45-60 minutes on a call; we write, you approve before publication | `contribution: interview` issue |
| **Section** | Write one section of an article someone else is leading | Comment on the article's issue |

Contributing does not require a GitHub account. If issues and pull requests are not your tooling, say it in Discord or email and someone will carry it into the repo for you, with credit.

## The map

`/map` lists all articles and main acts with a live status:

- `published` - live, versioned, open to correction
- `in production` - has a lead author and a slot in a season
- `open for contributors` - outlined, unclaimed, yours if you want it
- `looking for voices` - the article is being written, but it needs practitioners: someone who has run a co-production, closed a studio, migrated off spreadsheets
- `not yet outlined` - later acts, no structure yet

The map is the source of truth. If the map and this document disagree, the map is right and this document needs a PR.

**Acts publish in numbered order.** Act 0 first, Act 9 last, roughly one month per act. That doesn't mean Act 7 can't be researched now - see [the timeline](#the-production-timeline) - but it won't publish out of sequence.

## The production timeline

[[TBD]]

Every article moves through the same four gates. Contributors work three acts ahead of what readers see.

esearch and booking, Drafting, Editing, Publication

Each season also has a **week 0 dark week** (trailer, outline opened for comment, contributor call) and a **week 3 finale** (the act compiled into a downloadable PDF). 

Line B - Company News and Customer Stories - runs on its own interview slot, independent of the season calendar. Those are commissioned directly; open a `contribution: interview` issue or ask in Discord.

## Repository structure

[[TBD]]

```
/content
  /act-0-entering-the-industry
    00-index.md              # act outline, status, editor
    01-the-map.md
    02-five-studios-five-business-models.md
    ...
  /act-1-founding
  ...
/interviews                  # transcripts, cleared for use, one file per interview
/data                        # datasets behind charts, CSV, with a README per set
/assets                      # diagrams, charts, photos
/editorial
  style-guide.md             # the long version of House style
  glossary.md                # terminology, disciplines, territories
  interview-kit.md           # question banks, consent form, release template
  templates/article.md       # start here for a new article
/map                         # the hub page source
```

One article, one file. Filenames are `NN-kebab-case-slug.md`, numbered by position within the act.

## Frontmatter

[[TBD]]

Every article carries this block. It drives the map, the credits, the changelog, and the review reminders.

```yaml
---
title: "Why studios lose money while fully booked"
act: 4
position: 3
slug: why-studios-lose-money-while-fully-booked
status: in-production        # open | in-production | community-round | published
tags: [studio-operations]
authors:
  - name: Full Name
    role: Studio Manager, Studio Name
    link: https://…
contributors:                # sections, research, data, testimony
  - name: Full Name
    contribution: "Bid teardown, Act 4 §3"
reviewers:
  - name: Full Name
    role: Executive Producer, Studio Name
interviews: [interviews/2026-03-studio-name.md]
version: 0.4
last_reviewed: 2026-03-14
next_review: 2027-03-14      # default: 12 months; 6 for tooling and AI articles
season_slot: 2026-W22
---
```

Rules that matter:

- **`authors`** is for people who wrote prose. **`contributors`** is for everyone else who changed the article - research, a corrected number, a paragraph, a story. Being generous here is the house policy.
- **`reviewers`** are named practitioners who read it for accuracy. A reviewer is not an endorsement of every claim; it means someone with standing read it and flagged what was wrong.
- **`last_reviewed`** is not the last edit. It's the last time someone deliberately checked the article was still true. Fixing a typo does not move it.
- Anyone can be listed as `anonymous` with a role and territory instead of a name. See below.

## Style Guide

**Write for a working founder at 11pm.** The reader runs a studio, or is about to. They are tired, they are competent, and they have been sold a lot of nonsense. They do not need animation explained to them.

**Specific over general.** "Payment terms of 60 days on a six-month project means you're financing two payrolls" beats "cash flow is important." Every general claim should be followed, within a paragraph, by something concrete enough to argue with.

**Numbers with provenance.** Any figure gets a source, a date, and a scope. "€X per second" is meaningless without discipline, territory, year, and what's included. If you can't scope it, cut it.

**Name the trade-off.** No article in this book recommends a single correct answer to a decision that real studios split on. Give the reader the shape of the choice and who each option suits.

**Structure**
- One-paragraph opening that states the actual problem. No throat-clearing about how the industry is changing.
- H2 sections. H3 sparingly. A reader should be able to scan the H2s and know whether to read.
- Tables for comparisons across disciplines or territories. They travel well and they get quoted.
- Close with what changes on Monday - a checklist, a set of questions to ask, a number to go and find in your own accounts.

**Length**: most articles land between 1,800 and 3,000 words. Discipline deep-dives run longer. Length is an output, not a target; if it's 1,200 words and complete, it's done.

**Voice**: first person plural for the blog's voice, first person singular when an author is telling their own story - clearly attributed. Both are fine in one article if it's obvious which is which.

**Quotability is a design goal.** Every article should contain two or three sentences that survive being pulled out and posted alone. Write them on purpose.

**Avoid**: hedge stacks ("it can sometimes be the case that"), the word "leverage" as a verb, invented statistics, LinkedIn cadence, and any sentence that would be equally true of a bakery.

The full style guide, including terminology and territory conventions, is at `/editorial/style-guide.md`.

## Evidence, sources and anonymity

Much of the most valuable material in this book is commercially sensitive: rates, margins, why a project failed, what an acquisition actually paid. We take that seriously and so should you.

**Interview subjects control their own attribution.** Every interviewee chooses, in writing, one of:

- **Named** - name, role, studio.
- **Role-attributed** - "an executive producer at a 40-person 2D series studio in France."
- **Background** - informs the article, is not quoted or referenced.

The choice is confirmed *after* they see how they've been used, not before the call. Nobody is talked into being named.

**Never publish, in any form:**

- A named client's rates, terms or internal problems without that client's written agreement
- Anything covered by an NDA the contributor is subject to - if you're not sure whether you can say it, you can't
- Individually identifying details about an employee in a story about layoffs, conflict or dismissal
- Salary or rate data traceable to a specific person

**Aggregate where you can.** Five studios' bid structures reported as a range with a sample description is more useful, more publishable, and safer than one studio's spreadsheet.

**Every interview needs a signed release** before its material goes into a draft. The template and consent language are in `/editorial/interview-kit.md`. Transcripts live in `/interviews`, but only ones cleared for the repo - anything sensitive stays out of git entirely and the article cites it as a private interview with a date.

**Fact-checking.** Before a draft leaves T-4, every number in it needs a source line in the PR - either a public link, a dataset in `/data`, or an interview reference. Editors check these. An unsourced number is a blocker, not a nit.

## Pull requests

**Branches**: `act-N/slug` for articles, `fix/slug-short-description` for corrections, `data/set-name` for datasets.

**Commits**: plain English, present tense. `Add Quebec tax credit stacking example` is fine. There's no commit convention to memorise.

**One article per PR.** Corrections to multiple articles can share a PR if they're the same correction.

**PR description should say**: what changed, what's still open, and who you'd like to read it. Tag the article's issue.

**Open drafts early.** A draft PR at 20% is more useful to this project than a polished one at T-2. Mark it as a GitHub draft and nobody will treat it as finished.

**Small corrections skip all of this.** Use the *Suggest an edit* link at the foot of every published article - it opens GitHub's web editor on the right file and makes the PR for you. Typos get merged without ceremony.

## Review

Two things have to happen before merge:

- **Editorial review** - structure, voice, whether it earns its place in the act. Done by the act's editor, named in the act's `00-index.md`.
- **Practitioner review** - at least one named reviewer who has actually done the thing the article describes. For territory-specific material (legal structures, tax credits, employment law), a reviewer from that territory.

Reviewers are asked to be blunt. If something is wrong, say it's wrong in the comment; there's no need to soften it into a suggestion. Authors are asked not to defend a draft that a practitioner says doesn't match reality - check it, then change it or find out why you disagree.

Disagreements that survive review get published as disagreements. "Studios split on this, here's the case each way" is a legitimate outcome and often the more honest article.

Target turnaround is one week per review round. Chase in Discord if it stalls.

## Credit

- Everyone who changed an article appears in its frontmatter and in the visible credit block at the foot of the page, with their role and studio and a link they choose.
- Article credits carry into the season's compiled PDF chapter and into the blog.
- Anonymous and role-attributed contributors are credited in the same places, in the form they chose.
- Contributors keep a permanent profile page listing everything they've touched across the blog.
- Corrections count. Someone who fixes three numbers across three acts is a contributor to three articles.

We don't do ghostwriting and we don't do uncredited editing. If you rewrote a section, your name goes on it.

## Versioning and changelogs

Published articles are living documents.

- **1.0** - first publication.
- **Patch (1.0 → 1.1)** - corrections, clarifications, updated figures. Changelog entry, no re-announcement.
- **Minor (1.1 → 1.2)** - a new section, a new discipline covered, substantial new material. Changelog entry.
- **Major (1.x → 2.0)** - the argument changed, or the ground did. Re-published as an event: newsletter, social, and a note at the top of the article explaining what changed and why.

Every article carries a visible changelog. Every revision names who made it.

**Review cadence**: 12 months by default; 6 months for anything covering tooling, AI, real-time, or funding programmes. When `next_review` passes, an issue opens automatically and the article gets a "last reviewed" note in its header until someone checks it. Volunteering for review passes on old articles is one of the most useful things you can do.

## Licensing and IP

[[TBD]]

- Text and diagrams, Datasets, Any code, Interview material, The compiled PDF chapters and the finished blog

## What we don't publish

- Vendor content. Tools get discussed on the merits, including tools built by people involved in this book. If an author has a commercial interest in something an article recommends, it's disclosed in the frontmatter and visibly on the page. Undisclosed, it's a revert.
- Named criticism of specific studios, clients or individuals. Failures are covered - anonymised, structurally, for what they teach.
- Rate cards presented as benchmarks. Ranges with scope and provenance, yes. A number people will quote at each other in negotiations without context, no.
- Speculation about ongoing deals, layoffs or acquisitions that hasn't been confirmed.
- Anything that reads like it was generated and not checked. Use whatever tools you like to draft; you are answerable for every claim that ships under your name.

## Code of conduct

This is an industry with long memories and small rooms. Everyone here is doing this alongside a real job.

Be precise, be generous with credit, and argue about the work rather than the person. Full text in [`CODE_OF_CONDUCT.md`](./CODE_OF_CONDUCT.md); it's enforced, and reports go to the address listed there.

## Where to talk

- **Discord** - `[link]` - day-to-day, drafts, questions, "does anyone know how X works in Ireland"
- **Issues** - claiming articles, proposals, corrections with a paper trail
- **Email** - `[address]` - anything that shouldn't be public, including sensitive testimony

If you're not sure where something goes, Discord. Someone will point you.

*This document is versioned like everything else. If a rule here made your contribution harder than it needed to be, that's a bug - open a PR.*