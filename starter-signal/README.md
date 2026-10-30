# Signal · starter design system

Bold and technical. For software, startups and product launches.

## What's in here
| File | What it is |
|---|---|
| `storybook.html` | Every colour, type size and component on one page. Open it first. |
| `index.html`, `pricing.html`, `about.html`, `contact.html` | A sample four-page website built only from the system |
| `assets/tokens.css` | All values: colours, fonts, sizes, radii, motion. Change these to make it yours. |
| `assets/components.css` | All components. Built from tokens only. |
| `SKILL.md` | The design rules, written for Claude |
| `CLAUDE.md` | The context file. Start every new chat or Claude Code session by pointing at it. |
| `netlify.toml` | Lets Netlify publish the folder as it is |

## Use it tonight
1. Open `storybook.html` and `index.html` in your browser to see the system.
2. In Claude, start a new chat (ideally in a Project). Attach `CLAUDE.md`, `SKILL.md`, `assets/tokens.css` and `assets/components.css`.
3. Ask Claude to rewrite the sample pages with your business, your words and your prices, keeping to the system.
4. Make it yours: ask Claude to change the tokens (accent colour, fonts, radius). Every page follows.
5. Drag the whole folder onto Netlify. Your site is live, and the contact form works.

## Fonts
Self-hosted in `assets/fonts`, so no requests go to Google (good for GDPR). All fonts are under the SIL Open Font License; licence files are included.
