# Prompts

Every prompt from the workshop, in order. Replace anything in [brackets].

---

## Set up

**Project instructions** (paste into your Claude Project's instructions)
```
Follow CLAUDE.md and SKILL.md for every answer. Our Git: design system at github.com/[you]/[yourbrand]-design-system, website at github.com/[you]/[yourbrand]-website. Build only from the design system. Claude Code never makes a design decision; when something isn't defined, ask me first.
```

**Fill in the context file**
```
Help me fill in CLAUDE.md for my business. Ask me one question at a time: what I do, who it's for, what makes me different, and the links to my two repositories.
```

---

## Before stage 1: inspiration and versions

**Turn references into direction**
```
Here are references I like: [attach screenshots]. For each one, tell me what makes it work: layout, type, colour, motion, storytelling. Then suggest how I could bring that feeling to my home page, using my design system.
```

**Three directions**
```
Design three versions of my home page hero, using only my design system: 1. calm and editorial, 2. bold with motion, 3. visual storytelling as you scroll. Show them side by side so I can compare them. Then tell me which fits my audience best and why.
```

---

## Stage 1 · Design in chat

**Prototype**
```
Build my home page following the skeleton: navigation, hero, what I do, how it works, proof, closing call to action, footer. Use the direction we picked and only my design system. Show it to me, then show me the phone width.
```

## Stage 2 · Update the system

**System or page?**
```
Look at the home page we just made. List every decision that should become part of the design system: new tokens, new components, new rules. Then give me the updated tokens.css, components.css, storybook.html and SKILL.md, and the final page as prototypes/home.html.
```

## Stage 3 · Push to Git

No prompt. In GitHub Desktop, in `yourbrand-design-system`: write a short summary, Commit, Push origin.

## Stage 4 · Build with Claude Code

**To Claude Code** (in your `yourbrand-website` folder)
```
Read CLAUDE.md. First, get the latest from github.com/[you]/[yourbrand]-design-system and update this website's tokens and components to match. Then build index.html from prototypes/home.html in that repository. Never make a design decision: if something isn't defined, stop and ask me with two or three options. Work on a new branch called home-page. When done, tell me what you built and every open question.
```

## Stage 5 · Test on localhost

**Run and test** (to Claude Code)
```
Start a local server for this site and give me the address. Then run Lighthouse on the home page for mobile and desktop, check every breakpoint and every link, and report the scores and anything that breaks the design system.
```

**Not OK? Back to chat** (to Claude chat)
```
Here is Claude Code's report: [paste]. Which of these change the design system and which are page fixes? Write the next prompt for Claude Code.
```

## Stage 6 · Pull request

**To Claude Code**
```
Everything works. Commit the changes on the home-page branch with a clear message, push it, and open a pull request to main with a summary of what changed and the test results.
```

Then on GitHub: wait for the Netlify check, open the Deploy Preview, check it on your phone, Merge.

---

## When you're stuck

**To understand**
```
Explain [Git / a pull request / DNS] like you're talking to a third grader. Then give me one example from building a website.
```

**To do it**
```
I want to [connect my domain to Netlify]. Walk me through it step by step. One step at a time, and wait until I say done.
```

**When stuck**
```
Here's what I see on my screen: [paste the error]. What does it mean and what do I do next? Keep it simple.
```
