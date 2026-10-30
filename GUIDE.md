# From sample to a live website

The kits in this repo are samples. This guide takes you from a sample to your own design system and a live website, the way a design team works with Claude. It follows the workshop deck step by step. Every prompt is also in [PROMPTS.md](PROMPTS.md), ready to copy.

**New words?** Git, push, pull request, domain, CMS and more are explained in plain language in [GLOSSARY.md](GLOSSARY.md). When in doubt, ask Claude: *"Explain this like I'm a third grader, then walk me through it one step at a time."*

---

## The roles

| Role | Tool | Job |
|---|---|---|
| The brain | Claude chat | Think, decide, design, prototype, write prompts |
| The hands | Claude Code | Build, run it locally, test, open pull requests. Never decides design. |
| The source of truth | GitHub | Holds the design system and the website. If it's not in Git, it doesn't exist. |
| The window | GitHub Desktop | See changes, commit, push and merge without the command line |

**The rules:** build only from the design system. Claude Code never makes a design decision: if something isn't defined, it stops and asks with options.

---

## The loop

1. **Design in chat.** Prototype the page in Claude chat. Try versions. Fix phone, tablet and motion there.
2. **Update the system.** Anything reused or a rule goes into the design system. The page goes into `prototypes/`.
3. **Push to Git.** Push your design-system repository with GitHub Desktop.
4. **Build with Code.** Claude Code updates your website from the design system and builds the page, on a branch.
5. **Test on localhost.** Phone, desktop, links, Lighthouse. Not OK? The report goes back to stage 1, in chat.
6. **Pull request.** Open the Netlify preview link, check it, merge. The site goes live.

---

## Part 1 · Get set up

### 1. Five accounts and apps
- **Claude**, signed in at claude.ai
- **GitHub**, a free account at github.com/signup
- **GitHub Desktop**, a free app from desktop.github.com, signed in with GitHub
- **Claude Code**, in the Claude desktop app or your terminal, signed in with Claude
- **Netlify**, a free account at netlify.com, signed up with your GitHub account

### 2. Get the starter kit
Any of these works:
- **Download ZIP:** on this repo's page, Code, then Download ZIP. Unzip.
- **GitHub Desktop:** File, Clone repository, URL tab, paste `https://github.com/hoomanab01/web-style-guide`, Clone.
- **Terminal:** `git clone https://github.com/hoomanab01/web-style-guide`

Pick the kit closest to your brand: `starter-paper`, `starter-clay` or `starter-signal`. The kit is your starting point, not your repository.

### 3. Create two repositories

| Repository | Its job | Copy in from your kit |
|---|---|---|
| `yourbrand-design-system` | Where design decisions live. Claude chat works from here. | `assets/`, `storybook.html`, `SKILL.md`, `CLAUDE.md`, `prototypes/` |
| `yourbrand-website` | Where the site lives. Claude Code builds here, Netlify publishes it. | the pages (`*.html`), `assets/`, `netlify.toml`, `CLAUDE.md` |

For each one, in GitHub Desktop: File, New repository, enter the name, Create. Copy the files in. Commit, then Publish repository. Private is fine.

### 4. Connect Claude to your GitHub
- **Claude chat:** Settings, Connectors, connect GitHub and allow both repositories. You can now add files to a Project straight from `yourbrand-design-system`.
- **Claude Code:** open it in your `yourbrand-website` folder. The first time it pushes, it asks you to sign in to GitHub. Sign in and allow access.

### 5. Set up your context in Claude
1. Create a Project named after your website.
2. Add to the Project, from `yourbrand-design-system`: `CLAUDE.md`, `SKILL.md`, `assets/` and `storybook.html`.
3. Paste the Project instructions from [PROMPTS.md](PROMPTS.md).
4. Ask Claude to fill in `CLAUDE.md` with you (prompt in PROMPTS.md), then save it in both repositories.

`CLAUDE.md` is the context file. Claude Code reads it automatically. Your Project starts every chat from it.

### 6. Turn on Anthropic's skills
In Claude: Settings, Capabilities, turn on Skills, then turn on:

| Skill | What it helps with |
|---|---|
| frontend-design | Designed pages instead of generic ones: layout, type, motion |
| web-artifacts-builder | Bigger interactive pages with several parts |
| canvas-design | Visuals and posters, for moodboards and imagery |
| theme-factory | Trying colour and font themes quickly |
| skill-creator | Turning your design rules into a skill later |

Your kit's `SKILL.md` sits in your Project, so Claude follows your design rules too.

### 7. Connect Netlify to `yourbrand-website`
1. In Netlify: Add new project, Import an existing project, GitHub.
2. Choose `yourbrand-website`.
3. Check the settings, then Deploy:

| Field | Value for the kits |
|---|---|
| Branch to deploy | `main` |
| Base directory | empty |
| Build command | empty |
| Publish directory | `.` |

4. Project configuration, Build and deploy, Branches: add `staging` as a branch deploy.
5. Change the project name to `yourbrand`, so the address is `yourbrand.netlify.app`.

**What the addresses mean:**
- `main` is the live site at `yourbrand.netlify.app`. It changes only when you merge.
- `staging` is a private rehearsal copy at `staging--yourbrand.netlify.app`.
- Every pull request gets a **preview link**: a temporary copy of the site with just that change. Netlify puts the link in the pull request.

---

## Part 2 · Build the home page around the loop

### The skeleton

| Section | What it needs |
|---|---|
| Navigation | Logo, four links, one button |
| Hero | One headline that says what you do. One line under it. One primary button. |
| What you do | Three things you offer, each with a title and one sentence |
| How it works | Three steps, from first contact to result |
| Proof | A real quote, a client logo or a number, with its source |
| Closing call to action | One line and one button: get in touch |
| Footer | Links, Impressum, privacy |

### Get inspired, then make versions
1. Collect 5 to 10 references on Pinterest or from sites you love. Screenshot them.
2. Drop them into your Claude chat and say what you like about each.
3. Ask for three versions (calm and editorial, bold with motion, visual storytelling) and compare them side by side. Pick one.

### Stage 1 · Design in chat
Prototype the home page from the skeleton. Check it: a stranger gets what you do in five seconds, one clear next step, works on a phone, sounds like you.

### Stage 2 · Update the system
Ask Claude what should become part of the design system. Save the updated `tokens.css`, `components.css`, `storybook.html`, `SKILL.md` and `prototypes/home.html` into `yourbrand-design-system`.

### Stage 3 · Push to Git
GitHub Desktop, `yourbrand-design-system`: write a short summary, Commit, Push origin.

### Stage 4 · Build with Claude Code
Open Claude Code in `yourbrand-website` and paste the handover prompt. It gets the latest design system, builds `index.html` from the prototype on a branch, and asks you about anything undefined.

### Stage 5 · Test on localhost
Ask Claude Code to start a local server and run Lighthouse. Check phone, tablet, desktop, motion and every link. Not OK? Paste the report into Claude chat and get the next prompt.

### Stage 6 · Pull request
Ask Claude Code to open a pull request. On GitHub, wait for the Netlify check, open the Deploy Preview, check it on your phone, then Merge. `yourbrand.netlify.app` updates in a minute.

**The next page is the same loop.**

---

## Homework

### 1. Make the contact form work
1. Build the contact page around the loop.
2. In Netlify: Forms, turn on form detection.
3. Deploy again so Netlify finds the form.
4. Forms, Form notifications: add an email to your inbox.
5. Send yourself a message from the live site.

GDPR: a name and an email are personal data. Before real customers use the form, add a privacy notice, an Impressum, and a data processing agreement with every service that touches the form. Not legal advice.

### 2. Your own domain
**Easiest:** Netlify, Domain management, Add a domain, Buy a new domain. Netlify connects it and turns on HTTPS.

**One you already own:**
1. Domain management, Add a domain you already own, Verify, Add domain.
2. Where your domain's DNS is managed, add the record:

| You want | Add this record |
|---|---|
| `www` or a subdomain | CNAME, pointing to `yourbrand.netlify.app` |
| `yourbrand.com` | A record `@`, to the IP Netlify shows |

3. If Netlify asks for a TXT record, add it too.
4. Wait a few minutes, then Domain management, HTTPS, Verify DNS configuration.

- DNS on Cloudflare? Set the record to DNS only (grey cloud).
- Never point a live domain at a test site. Try things on a subdomain.
- Don't move nameservers on a domain you already use: it moves your email records too.

### Later: do you need a CMS?
See [GLOSSARY.md](GLOSSARY.md#do-you-need-a-cms). If you're the only editor and happy asking Claude, you don't need one yet.

---

## Checklist before a site goes public
- [ ] Every page built from the design system only
- [ ] Phone, tablet, desktop checked; no sideways scrolling
- [ ] Lighthouse checked on mobile and desktop
- [ ] Contact form tested end to end
- [ ] Real content and real testimonials only, with permission
- [ ] Impressum and privacy notice (required in Germany)
- [ ] `SKILL.md` and `CLAUDE.md` up to date in both repositories
