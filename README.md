# Mortell-Miller Collab Notebook

A private, static HTML website for Art Mortell and Mike Miller — tracking tasks, ideas, projects, key people, and documents as the collaboration grows.

Hosted via GitHub Pages. No server, no database, no login required. All task edits are saved locally in the browser (localStorage).

---

## Pages

| File | Purpose |
|------|---------|
| `index.html` | Home/landing page with links to all sections |
| `tasks.html` | Task & assignment tracker with editable fields |
| `momentum.html` | Dedicated Momentum Work page — Jack's project, workshops, Momentum team |
| `ideas.html` | The 20-Idea Board with status filters |
| `people.html` | Key people in the network |
| `docs.html` | Docs, books, videos, and file references |
| `archive.html` | Completed tasks — check off a task on Tasks page to send it here |

---

## How to Update Content

All data lives in the `DATA` or `DATA_TASKS` JavaScript object near the top of each HTML file — clearly marked with comments. No build tools, no dependencies.

### Adding or editing a task (tasks.html)
Find the `DATA_TASKS` array and add/edit an entry:
```js
{ priority: "high", task: "Your task description", owner: "mike", due: "Fri June 6", context: "Optional context", done: false }
```
- `priority`: `high` | `med` | `low`
- `owner`: `mike` | `art` | `momentum`
- `done`: set to `true` to pre-populate the archive

### Adding a Momentum task (momentum.html)
Same format inside the `DATA.tasks` array in `momentum.html`.

### Adding an idea (ideas.html)
Find the `IDEAS` array:
```js
{ num: "Idea 14", title: "Your Idea Title", desc: "Description.", status: "queued", mode: "Mike Leads" }
```
- `status`: `momentum` | `active` | `assigned` | `queued` | `parked`

### Adding a person (people.html)
Find the `PEOPLE` array:
```js
{ name: "Full Name", role: "Title / Role", detail: "Background notes.", contact: "email · phone" }
```

### Adding a doc (docs.html)
Find the `DOCS` array:
```js
{ icon: "📄", name: "Document Name", desc: "Short description.", url: "https://..." }
```
Leave `url` as `""` if there's no link.

---

## How Editing Works (Browser)

On the Tasks and Momentum pages, three columns are editable directly in the browser:

- **Task** — click to edit the task text
- **Notes** — free-form working notes
- **Context** — background or reference info

All edits save automatically on blur (when you click away) and persist in `localStorage`. They survive page refreshes but are browser-specific — edits made on one device won't appear on another. For shared updates, edit the source HTML and push to GitHub.

---

## Archive

When a task is checked off on `tasks.html`, it disappears from the active list and appears on `archive.html`. To restore a task, uncheck it or click **↩ Restore** on the archive page.

---

## Deployment

1. Edit the HTML files directly
2. Commit and push to GitHub
3. GitHub Pages serves the site automatically from the repo root

All 7 files must stay in the same directory for navigation links to work correctly.

---

## File Locations

- **Repo / website files:** `Mortell-MIller WEbsite/`
- **Project context docs:** `/Volumes/VADER/Projects/Momentum Work, INC/Momentum_Art Mortell/`

---

*Private — Mortell-Miller Collaboration · Updated June 2026*
