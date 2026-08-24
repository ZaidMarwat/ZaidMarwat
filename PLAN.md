# Making github.com/ZaidMarwat worth clicking

Your resume sends recruiters here. Right now they find an anonymous account with a bare
Podman fork and an undescribed task manager. Everything below is ordered by impact per
minute spent.

---

## Tier 1 — do these today, ~20 minutes total

### 1. Publish the profile README  *(biggest single win)*

GitHub renders `README.md` from a repo named after you at the top of your profile. You
don't have that repo. Most students don't, which is exactly why it stands out.

```bash
cd ~/Desktop/github-profile
git init && git add README.md
git commit -m "Add profile README"
gh repo create ZaidMarwat --public --source=. --push
```

No `gh` CLI? Create a **public** repo named exactly `ZaidMarwat` on github.com, tick
nothing, then:

```bash
git remote add origin https://github.com/ZaidMarwat/ZaidMarwat.git
git branch -M main && git push -u origin main
```

### 2. Fill in the profile fields — all four are empty

github.com/settings/profile

| Field | Set it to |
|---|---|
| Name | `Zaid Marwat` |
| Bio | `CS @ UT Austin '27 · infrastructure, Linux, distributed systems · patent holder` |
| Location | `Austin, TX` |
| Website | `https://zaidmarwat.pages.dev` |

An empty name field means you show up as a username everywhere on GitHub, including on
your Podman PR.

### 3. Pin your repos

Profile → Customize your pins. Order matters; the first two get looked at.

1. `ZaidMarwat` (the profile repo — pins the README's own source, which reads as deliberate)
2. `task_manager` — **only after step 4**
3. `podman` fork — see the note below

---

## Tier 2 — this week

### 4. Give `task_manager` a description and a README

It is Python, 17KB, no description, untouched since October 2025. Right now it is a
liability: a recruiter opens it, finds nothing explaining what it does, and leaves.

Two options, and either beats the current state:

- **Fix it.** Add a one-line GitHub description, plus a README covering: what problem it
  solves, how to run it, and one thing that was non-obvious to build. Three paragraphs is
  plenty.
- **Archive it.** Settings → Archive. An archived repo reads as "finished," not abandoned.

### 5. Push the personal site

`~/Desktop/zaid-site` is your best-looking artifact and it is live. A repo with a real
README, a link to the deployed site, and legible source is worth more than most student
projects. It also demonstrates the thing recruiters cannot verify from a resume: that your
code looks like something a colleague would want to work in.

```bash
cd ~/Desktop/zaid-site
git init && git add -A
git commit -m "Personal site: terminal-first, deployed on Cloudflare Pages"
gh repo create zaidmarwat.dev --public --source=. --push
```

### 6. About the Podman fork

Your fork will always look empty — that is just how forking works, and nobody holds it
against you. What matters is that the **PR** is linked, which the profile README now does.

The fork is worth pinning *only* because a visitor clicking it lands on Podman's codebase
with your branch in the dropdown. If that feels like a stretch, pin something else.

---

## Tier 3 — higher effort, real payoff

### 7. The BCI wheelchair

Your most distinctive project has no public code. Even a partial repo — the EEG
preprocessing, the classification model, a README with the story and a link to the
publication — would be the most interesting thing on your profile.

**Check first:** it was a team project, so get your teammates' agreement. If any subject
data was recorded from a real person, that data does not go in the repo under any
circumstances. Code and synthetic or public sample data only.

### 8. The thermal-imaging system — get permission before anything

This one is patented. Published source can interact badly with patent scope, and there are
likely co-inventors and possibly an assignee with rights. **Do not push this until you have
checked with whoever holds the patent rights.** The patent itself is already public and
already linked from the README, which captures most of the credibility anyway.

### 9. Never push

Texas Instruments and Visa code. Both proprietary, both a fireable offence and a
retracted-offer offence. The resume bullets carry that work; the repos never should.

---

## How to describe the Podman PR — accuracy matters

The PR is **open, not merged**. These are all true:

- "Authored a fix for Podman's ancestor filter"
- "Opened a PR against Podman resolving image names to IDs in container filtering"
- "Contributed a correctness fix to Podman (PR #27778)"

These are **not** true yet, and an interviewer will check:

- "Merged a fix into Podman"
- "My code ships in Podman"

If it gets merged, update the resume bullet and this README the same day. If it goes stale,
a polite ping on the PR is normal and often all it takes.

---

## What this fixes

| Before | After |
|---|---|
| Anonymous account, no name or bio | Named, with a one-line pitch and a link to your site |
| Best work (Podman PR) invisible | Linked at the top with the technical reasoning |
| 2 repos, one a bare fork, one undescribed | Curated pins, each with a README that explains itself |
| Resume points somewhere that undercuts it | Resume points somewhere that corroborates it |
