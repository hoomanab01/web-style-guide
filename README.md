# web-style-guide

Sample style guides as a starter for building websites with Claude.

Three ready-to-use design systems. Each one is a complete, working four-page website (home, pricing, about, contact) built only from its own tokens and components, so you start from something designed instead of a blank page.

| Kit | Feel | Good for |
|---|---|---|
| [`starter-paper`](starter-paper) | Editorial and calm | Consultants, studios, writers, advisors |
| [`starter-clay`](starter-clay) | Warm and friendly | Local businesses, food, wellness, makers |
| [`starter-signal`](starter-signal) | Bold and technical | Software, startups, product launches |

## What's in each kit

| File | What it is |
|---|---|
| `storybook.html` | Every colour, type size and component on one page. Open it first. |
| `index.html`, `pricing.html`, `about.html`, `contact.html` | A sample website built only from the system |
| `thanks.html` | Shown after the contact form is sent |
| `assets/tokens.css` | All values: colours, fonts, sizes, radii, motion. Change these to make it yours. |
| `assets/components.css` | All components, built from tokens only |
| `SKILL.md` | The design rules, written for Claude |
| `CLAUDE.md` | The context file. Point every new chat or Claude Code session at it. |
| `netlify.toml` | Lets Netlify publish the folder as it is |

## How to use a kit

1. Pick a kit and open its `storybook.html` and `index.html` in your browser.
2. In Claude, start a new chat (ideally in a Project). Attach the kit's `CLAUDE.md`, `SKILL.md`, `assets/tokens.css` and `assets/components.css`.
3. Ask Claude to rewrite the sample pages with your business, your words and your prices, keeping to the system.
4. Make it yours: ask Claude to change the tokens (accent colour, fonts, corner radius). Every page follows.
5. Drag the kit folder onto Netlify. Your site is live, and the contact form works.

## Next: make it your own

The kits are samples. [GUIDE.md](GUIDE.md) takes you from a sample to your own style guide, design skill and storybook in Claude chat, then to Claude Code, localhost, and a pull request.

## The rule

Build only from the design system. No one-off colours, sizes or components on a page. A new value goes into `tokens.css` first, then the pages use it.

## Notes

- Sample businesses and placeholder quotes are fictional. Replace them with your own content and real testimonials, with permission.
- Fonts are self-hosted in each kit's `assets/fonts` (no requests to Google, which helps with GDPR). All fonts are under the SIL Open Font License; licence files are included.
- Before sharing a site with real customers in Germany, add an Impressum and a privacy notice.

Made by Hooman Abbasi, Raise Studio.
