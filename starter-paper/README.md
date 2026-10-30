# Paper · starter design system

Editorial and calm. For consultants, studios, writers and advisors.

## What's in here
| File | What it is |
|---|---|
| `storybook.html` | Every colour, type size and component on one page. Open it first. |
| `index.html`, `pricing.html`, `about.html`, `contact.html` | A sample four-page website built only from the system |
| `assets/tokens.css` | All values: colours, fonts, sizes, radii, motion. Change these to make it yours. |
| `assets/components.css` | All components. Built from tokens only. |
| `SKILL.md` | The design rules, written for Claude |
| `CLAUDE.md` | The context file. Start every new chat or Claude Code session by pointing at it. |
| `prototypes/` | Where page designs from Claude chat go |
| `netlify.toml` | Lets Netlify publish the folder as it is |

## Use it
This kit is a starting point. You split it into two repositories of your own:

| Repository | Copy in from this kit |
|---|---|
| `yourbrand-design-system` | `assets/`, `storybook.html`, `SKILL.md`, `CLAUDE.md`, `prototypes/` |
| `yourbrand-website` | the pages (`*.html`), `assets/`, `netlify.toml`, `CLAUDE.md` |

Then follow [GUIDE.md](../GUIDE.md) at the root of this repo. Every prompt is in [PROMPTS.md](../PROMPTS.md).

## Fonts
Self-hosted in `assets/fonts`, so no requests go to Google (good for GDPR). All fonts are under the SIL Open Font License; licence files are included.
