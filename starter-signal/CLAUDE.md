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
- Every change goes to `staging` first, then `main`, through a pull request.
- Test every page on phone and desktop before calling it done.

## Rules for Claude Code
- Never make a design decision. Colours, fonts, spacing, layout, copy, motion and imagery are decided in Claude chat and live in the design system or the prototype.
- If something isn't defined there, stop and ask. Offer two or three options with a short reason for each. Don't pick one yourself.
- Use only tokens from `assets/tokens.css` and components from `assets/components.css`. Never hard-code a value.
- After building, run the site locally, test phone and desktop, and report what you built, what you tested and every open question, before opening a pull request.

## Current state
[What's done, what's next. Update this at the end of each session.]
