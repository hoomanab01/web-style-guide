# Words you'll hear, in plain language

You don't need to know all of this before you start. When you meet a word you don't know, come back here, or just ask Claude.

---

## How to learn anything here: ask Claude

This is how we learn new tools ourselves. Three prompts cover almost everything:

**To understand something:**
> Explain [Git / a pull request / DNS] like you're talking to a third grader. Then give me one example from building a website.

**To do something step by step:**
> I want to [buy a domain and connect it to Netlify]. Walk me through it step by step. Give me one step at a time and wait until I say "done" before the next one.

**When you're stuck:**
> Here's what I see on my screen: [paste the error or describe it]. What does it mean, and what do I do next? Keep it simple.

Asking is the skill. Nobody remembers all of this.

---

## Git and GitHub

**Git**
A save system for your project that remembers every version. Like "track changes" for a whole folder: you can always see what changed, who changed it, and go back.

**GitHub**
A website that keeps your Git project online, so it's backed up, shareable, and connected to other tools like Netlify and Claude.

**GitHub Desktop**
An app that lets you use Git with buttons instead of typing commands. Good for designers and anyone who doesn't live in a terminal.

**Repository (repo)**
One project folder that Git looks after. Your design system is one repo; your website can be another.

**Commit**
A saved snapshot of your work, with a short note saying what changed. "Updated the button colour." Think of it as pressing save with a label.

**Branch**
A safe copy of the project where you can try things without touching the live version. `main` is the real one. You make a branch like `new-homepage`, work there, and only bring it back when it's right.

**Push**
Send your saved commits from your computer up to GitHub.

**Pull**
Get the latest changes from GitHub down to your computer. Do this before you start working, so you're not working on an old version.

**Origin**
Git's nickname for "the copy on GitHub". **Push origin** just means "send my work to GitHub".

**Clone**
Download a whole repo from GitHub to your computer, including its history, the first time.

**Pull request (PR)**
A request that says: "I made these changes on my branch. Please check them and then add them to `main`." It's where changes get reviewed before they go live. On Netlify, every pull request gets its own preview link, so you can see the real site before saying yes.

**Merge**
Accepting a pull request: the changes from the branch are added to `main`. On Netlify, merging into `main` updates your live site.

**Merge conflict**
When two changes edit the same line and Git can't tell which one to keep. It asks you to choose. Claude can help you pick.

**Versioning**
Giving your project numbered versions, like an app: `v1.0.0`, `v1.1.0`, `v2.0.0`. The usual pattern:
- first number: big change that might break things (v**2**.0.0)
- second number: new things added (v1.**1**.0)
- third number: small fixes (v1.0.**1**)

**Tag**
A name pinned to one exact commit, usually a version number. "This is v1.2.0 of our design system." Useful so a website can say "I use design system v1.2.0" and nothing changes under its feet.

**Release**
A tag on GitHub with a short note about what's new. Your design system's changelog, in one place.

---

## Websites and hosting

**Hosting**
The computer on the internet that keeps your website's files and shows them to visitors. Netlify is a host.

**Deploy**
Putting the latest version of your site online.

**Build**
Turning your project into the finished files a browser can read. Plain HTML sites don't need a build. Frameworks like Astro do: `npm run build` creates the finished site in a `dist` folder.

**Localhost**
Your own computer pretending to be a web server, so you can see your site before it goes online. An address like `http://localhost:8000` only works on your machine.

**Staging**
A private rehearsal version of your site. You check it there, then publish to the real one.

**Deploy preview**
A temporary link Netlify makes for every pull request, so you can see the change on the real site before you merge it.

**Framework (Astro, Next.js)**
A toolkit that makes building websites faster, for example by letting you write the menu once instead of on every page. Astro is the closest to plain HTML and CSS.

**Lighthouse**
A free test built into Chrome that scores a page on speed, accessibility, SEO and good practice. Claude Code can run it for you.

---

## Domains

**Domain**
Your website's name on the internet: `yourbrand.com`. You rent it per year, usually for about the price of a few coffees, more for some endings.

**Subdomain**
A name in front of your domain: `shop.yourbrand.com`, `test.yourbrand.com`. Free once you own the domain.

**Registrar**
The shop where you buy a domain.

**Where to get one**
- **Inside Netlify** (Domain management, Buy a new domain): the easiest, because everything gets connected for you.
- **A registrar you already use**, or a German one for `.de` domains.
- Pick a name that's easy to say, easy to spell, and not too close to another company's name.

**DNS**
The internet's address book. It tells browsers which server your domain points to. "Adding a DNS record" means writing a line in that address book.

**CNAME / A record**
Two kinds of lines in the address book. A CNAME says "this name points to that name" (`test.yourbrand.com` to `yoursite.netlify.app`). An A record says "this name points to this server address".

**Nameservers**
Who manages your address book. If you move nameservers to Netlify, Netlify manages all your DNS, including email records, so be careful on a domain you already use.

**HTTPS / SSL certificate**
The lock in the browser bar. It means the connection is private. Netlify gives you one for free, automatically.

---

## Claude

**Claude chat**
Where you think, decide and design. It can show you a page as a preview.

**Claude Code**
Claude working inside your project folder: it reads and writes files, runs your site locally, tests it, and pushes to GitHub.

**Project (in Claude chat)**
A space where every chat shares the same files and instructions. Put your design system and context file there.

**Context file (`CLAUDE.md`)**
A short note that tells Claude what you're building and how. Claude Code reads it automatically; in Claude chat, add it to your Project.

**Skill (`SKILL.md`)**
Instructions Claude follows for a specific kind of work. Your design skill teaches Claude your design system.

**Design system**
All the decisions about how your brand looks, in one place: colours, fonts, spacing, buttons, forms. Pages are built from it.

**Token**
One named value in the design system, like `--color-accent: #A9461F`. Change the token, and everything using it changes.

**Storybook**
One page that shows every part of your design system, so you can check it before building pages.

---

## Do you need a CMS?

**CMS (content management system)**
An editing screen for your website's content, so you can change text, add blog posts or swap images without touching code.

**You probably don't need one if:**
- you're the only one editing
- the site changes a few times a month
- you're happy asking Claude: "Add a blog post about X" or "Change the price on the pricing page"

**You probably do if:**
- someone else edits the site (a client, a marketing team)
- you publish often, like a weekly blog
- people need to edit without Claude, Git or code

### Your options, from simple to powerful

| Option | How it works | Good for |
|---|---|---|
| **Claude is your CMS** | You ask Claude to change content; it edits the files | Solo founders, small sites |
| **A Git-based CMS** (Decap CMS, Sveltia CMS, Pages CMS, TinaCMS) | Adds an editing screen at `yoursite.com/admin`. Edits are saved as files in your repo, as commits. | Small teams, blogs, clients who want a simple editor |
| **A headless CMS** (Sanity, Storyblok, Contentful, Hygraph) | Content lives in the CMS's own app. Your site pulls it in when it's built. | Teams publishing a lot, several editors, approvals |

**"Headless"** means the CMS only stores and edits content. It doesn't decide how the site looks. Your design system does that.

### How a headless CMS connects to your site

1. You set up content types in the CMS, like "Blog post" with a title, image and text.
2. Your site (usually built with a framework like Astro) fetches that content when it builds.
3. When an editor clicks **Publish** in the CMS, it tells Netlify to rebuild the site. This uses a **build hook**: a private link Netlify gives you that starts a new build.
4. A minute later, the new content is live.

Ask Claude to set it up, step by step:

> I want my team to edit the blog without touching code. Compare a Git-based CMS and a headless CMS for my site, then recommend one. Once I choose, walk me through setting it up step by step, one step at a time.

**Before choosing:** check where the CMS stores data (for GDPR), what the free plan includes, and whether your editors find it easy. Have one of them try it before you decide.
