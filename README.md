# Mortell-Miller Collab Notebook

A private, single-page dashboard for tracking the Art Mortell / Mike Miller collaboration — ideas, tasks, key contacts, and project docs. Momentum Work is the primary mission.

---

## How to publish (first time)

1. Create a new GitHub repository (suggested name: `collab-notebook`)
2. Upload `index.html` and this `README.md` to the root of the repo
3. Go to **Settings → Pages**
4. Under **Source**, select `Deploy from a branch` → `main` → `/ (root)` → Save
5. GitHub will give you a live URL within a minute or two: `https://yourusername.github.io/collab-notebook/`

---

## How to update the site

All content lives in the `DATA` object near the top of `index.html` — roughly line 140. Edit that block, save, and push. The site updates immediately.

### Update the "last updated" date
```js
lastUpdated: "June 3, 2026",
```

### Add a task (permanent, visible to both)
Add an entry to `DATA.tasks`:
```js
{ priority: "high", task: "Your task description", owner: "mike", due: "Mon June 3", context: "Any extra context", done: false },
```
- `priority`: `"high"` / `"med"` / `"low"`
- `owner`: `"mike"` / `"art"` / `"momentum"`
- `done`: set to `true` to mark complete (shows as strikethrough)

### Mark a task done
Change `done: false` to `done: true`.

### Add an idea
Add an entry to `DATA.ideas`:
```js
{ num: "Idea 14", title: "Your Idea Title", desc: "Short description.", status: "queued", mode: "Mike Leads" },
```
- `status`: `"momentum"` / `"active"` / `"assigned"` / `"queued"` / `"parked"`

### Add a person
Add an entry to `DATA.people`:
```js
{ name: "Full Name", role: "Title / Role", detail: "Brief description.", contact: "email or phone" },
```

### Add a doc or link
Add an entry to `DATA.docs`:
```js
{ icon: "📄", name: "Document Name", desc: "What it is.", url: "https://link-if-applicable" },
```

### Update the Momentum Work status cards
Edit entries in `DATA.momentum`:
```js
{ label: "Jack Status", value: "Updated status here", sub: "Sub-detail line" },
```

---

## New Task button

The **New Task** button in the Tasks section lets you add tasks on the fly without editing the file. These save to your browser's local storage — they're visible on your device only and won't push to GitHub. To make a task permanent and shared, add it to `DATA.tasks` in `index.html` and push.

---

## File structure

```
/
├── index.html   — the entire site (edit DATA block to update content)
└── README.md    — this file
```

No build step. No dependencies. No server. Just push and it's live.
