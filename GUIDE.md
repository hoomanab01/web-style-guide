# From sample to your own website

The kits in this repo are samples. This guide takes you from a sample to your own design system, your own design skill and a live website, the way a design team works with Claude.

**The roles**

| Role | Tool | Job |
|---|---|---|
| The brain | Claude chat | Think, decide, design, prototype, write prompts |
| The hands | Claude Code | Build, run it locally, test, push |
| The source of truth | GitHub | Holds the design system and the site. If it's not in Git, it doesn't exist. |
| The window | GitHub Desktop | See changes, review and merge pull requests without the command line |

**New words?** Every term in this guide (Git, push, pull request, domain, CMS and more) is explained in plain language in [GLOSSARY.md](GLOSSARY.md). When in doubt, ask Claude: *"Explain this like I'm a third grader, then walk me through it one step at a time."*

**The rules:** build only from the design system. Claude Code never makes a design decision: if something isn't defined, it stops and asks. A new colour, size or component goes into the system first, then the pages use it.

---

## Step 1 · Start from a sample

1. Pick the kit closest to your brand: `starter-paper`, `starter-clay` or `starter-signal`.
2. Download it (on GitHub: **Code**, **Download ZIP**) or clone the repo.
3. In Claude, create a **Project** for your website. Add the kit's `CLAUDE.md`, `SKILL.md`, `assets/tokens.css`, `assets/components.css` and `storybook.html` to the project knowledge.
4. In the Project instructions, write: *"Follow CLAUDE.md and SKILL.md in this project for every answer."*

Every new chat in the Project now starts from the same context.

---

## Step 2 · Make the style guide yours (Claude chat)

Turn the sample's style guide into your brand: colours, type, shape, voice.

> Here is my business: [what you do, who it's for, three words for how it should feel]. Using the tokens in this project as the starting point, propose a style guide for my brand: colour palette with a role for each colour, a font pairing, corner radius, and five voice rules with a do and don't example each. Give me two directions to choose from. Keep every value as a token.

Then:

> Go with direction [A/B]. Give me the full updated tokens.css. Check text contrast is at least 4.5:1.

---

## Step 3 · Build the storybook (Claude chat)

The storybook is one page that shows every token and component. It's how you check the system before any page exists.

> Update storybook.html to use my new tokens. Show it to me. Then list anything that looks wrong or inconsistent.

Check it in the chat preview: colours, type sizes, buttons, cards, the form. Fix things here, not on pages.

---

## Step 4 · Write your design skill (Claude chat)

The design system is what your brand looks like. The skill is how Claude remembers it.

> Rewrite SKILL.md for my brand. Keep the structure: the look in one line, hard rules, components, page patterns, a checklist before delivering. Add my voice rules.

Keep the skill current: whenever a decision changes the system, ask Claude *"Should this go into the design skill?"* and update it.

Optional: to use it as a real skill in Claude, upload it in Claude's settings under Skills. In Claude Code, place it at `.claude/skills/my-design-system/SKILL.md` in the repo.

---

## Step 5 · Prototype each page (Claude chat)

> Design the home page for my business using only the design system. Sections: hero, what we do, how it works, proof, closing call to action. Show it to me.

Check in the preview:
- Phone, tablet and desktop: does it hold up?
- Motion: does it feel calm and consistent?
- Does every value come from the system?

For anything new, decide: **system or page?** Something used once stays on the page. Something reused, or a new rule, goes into the system: update `tokens.css`, `components.css`, the storybook and the skill first.

Repeat for pricing, about and contact.

---

## Step 6 · Put the system in Git

1. Create a repository on GitHub for your website. Use this kit's folder as the starting point.
2. Replace `assets/tokens.css`, `assets/components.css`, `storybook.html` and `SKILL.md` with your versions from Claude chat.
3. Save your page prototypes into a `prototypes/` folder.
4. Commit and push (GitHub Desktop: write a summary, **Commit to main**, **Push origin**).

Update the **Current state** section of `CLAUDE.md` before you push.

---

## Step 7 · Hand over to Claude Code

Ask Claude chat to write the prompt for Claude Code, so the brain briefs the hands:

> Write a prompt for Claude Code to build the [home] page from prototypes/[home].html in my repo. It should read CLAUDE.md and SKILL.md first, use only design system tokens and components, never make a design decision itself (if something isn't defined, stop and ask with options), run the site locally, test on phone and desktop, and report back before changing anything outside the page.

Then, in a terminal inside your repo:

```bash
claude
```

Paste the prompt.

---

## Step 8 · Check it on localhost

Ask Claude Code to run the site locally:

> Start a local server for this site and give me the address.

For a plain HTML site that's something like `python3 -m http.server 8000`, then open `http://localhost:8000`. Click through every page on your laptop and on your phone-sized browser window.

Ask Claude Code to test:

> Run Lighthouse on every page, mobile and desktop. Check every breakpoint and the contact form. Report scores and anything that doesn't follow the design system.

If Claude Code finds a problem it can't decide on, copy its report into Claude chat:

> Here is Claude Code's report: [paste]. Which of these change the design system and which are page fixes? Write the next prompt for Claude Code.

---

## Step 9 · Push and open a pull request

Never build straight on `main`. Work on a branch and open a pull request, so you can review before anything goes live.

> Create a branch called [page-home], commit the changes with a clear message, push it, and open a pull request to main with a summary of what changed and the test results.

Review it in GitHub Desktop or on GitHub. Netlify builds a **deploy preview** for every pull request, so you can open the real site before merging.

Happy? **Merge**. Netlify publishes `main` to your live site.

---

## The loop, in one line

**Chat thinks, Code builds, Git remembers.** Ideas go from chat to Code. Problems come back from Code to chat. Every change goes through a pull request.

---

## Checklist before a site goes public

- [ ] Every page built from the design system only
- [ ] Phone, tablet, desktop checked; no sideways scrolling
- [ ] Lighthouse checked on mobile and desktop
- [ ] Contact form tested end to end
- [ ] Real content and real testimonials only, with permission
- [ ] Impressum and privacy notice (required in Germany)
- [ ] `SKILL.md` and `CLAUDE.md` up to date
