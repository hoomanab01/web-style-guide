# Context

Read this first in every new chat or Claude Code session.

## What we're building
A website for [your business]: [one sentence on what you do and who it's for].
(Sample content in this kit is for Relay, simple uptime monitoring for small teams. Replace it with yours.)

## Source of truth
- Design system: this repo. Tokens in `assets/tokens.css`, components in `assets/components.css`, overview in `storybook.html`.
- Design rules: `SKILL.md`. Follow it for every page.
- Build only from the design system. Never invent colours, sizes or components. A new value goes into the design system first.

## Stack
Plain HTML, CSS and a little JavaScript. No build step. Hosted on Netlify. The contact form uses Netlify Forms.

## Pages
`index.html` (home) · `pricing.html` · `about.html` · `contact.html` · `thanks.html` (after the form)

## How we work
- Claude chat decides and prototypes. Claude Code builds and tests. GitHub is the source of truth.
- Every change goes to `staging` first, then `main`.
- Test every page on phone and desktop before calling it done.
- When something is unclear, stop and ask. Don't guess.

## Current state
[What's done, what's next. Update this at the end of each session.]
