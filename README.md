# Alberto Dal Corso — Portfolio

Single-page personal portfolio site for a Computer Games Programmer.
Static HTML, no build step, no dependencies: open `index.html` in a browser.

## Structure

```
Portfolio/
├─ index.html          # the whole site (markup + CSS + JS inlined)
├─ README.md
└─ media/              # project screenshots, one folder per project
   ├─ octonaut/        Screen1-4.jpg
   ├─ bloodrush/       Screen1-5.jpg
   ├─ leap/            Screen1-5.jpg
   ├─ antibot/         Screen1-4.jpg
   ├─ forestguardian/  Screen1-4.jpg
   ├─ urilux/          Screen1-3.jpg
   └─ topdown/         Screen1-3.jpg
```

## Sections

| Section | Content |
|---|---|
| Hero | Name, role, headline stats (3+ years, 8 projects, 4 game jams) |
| Projects | Card grid; clicking a card opens a modal |
| Experience | Goplay Universal, Fat Pigeon Games, Coding Giants Italia |
| Skills | Engines, languages, tools, 3D, mobile, methodology |
| Education | University of Westminster (BSc, First Class), I.I.S.S. Copernico-Pasoli |
| Contact | Email, LinkedIn, phone, location |

## Projects

| Project | Type | Engine / Tech |
|---|---|---|
| Octonaut | Group Project I — released on Steam as *Takotan* | MonoGame, C# |
| Blood Rush | Group Project III — VR | Unreal Engine 4, C++ |
| Leap | Tranzfuser 2020 (sponsored) | Unreal Engine 4, C++ |
| Antibot | Global Game Jam 2020 — "Repair" | Game jam, co-op |
| Forest Guardian | Ukie Green Game Jam 2019 — "Climate Change" | Game jam, stealth |
| Urilux | Westminster Game Jam 2019 — Most Appreciated | Game jam, co-op |
| Top Down | Ukie Game Jam 2018 — "Change" | Game jam, gravity mechanic |

## Editing

- **Project data** lives in the `const projects = [...]` array in the `<script>` block at the
  bottom of `index.html`. Each entry holds `id`, `type`, `title`, `year`, `role`, `team`,
  `duration`, `engine`, `language`, `youtube`, `images[]`, `concept`, `production`,
  `contributions[]`, `extra`, `tags[]`. The modal is rendered from this array.
- **Colors / theme**: CSS custom properties in `:root` at the top of the `<style>` block
  (`--bg`, `--surface`, `--border`, `--accent` `#00ff88`, `--accent2`, `--text`, `--muted`, `--card`).
- **Fonts**: Syne (headings) + IBM Plex Mono (body), loaded from Google Fonts.
- **Adding a project**: drop screenshots into `media/<slug>/`, add a card in the projects
  grid, and append an object to the `projects` array with matching `id`.

## Deploying

This repository **is** the live site: it is published by GitHub Pages at
<https://alby1998.github.io/> straight from the default branch. Any commit pushed
here goes live — there is no build step and no staging branch.

```bash
git add -A
git commit -m "your message"
git push
```

## Notes

- Historically the site was updated by uploading files through the GitHub web UI
  (hence the repeated "Add files via upload" commits). Prefer committing from a
  local clone instead — it keeps history meaningful and avoids case-duplicate files.
- **Filename case matters.** GitHub Pages serves from a case-sensitive filesystem,
  while Windows is case-insensitive. `Screen2.jpg` and `screen2.jpg` are two
  different files to Pages but collide on a Windows checkout. Keep the capitalised
  `ScreenN.jpg` convention used throughout `media/` and by `index.html`.
- This clone sets `core.autocrlf false` so line endings stay LF and edits do not
  show up as whole-file diffs.
- All assets are local; the only external requests are the Google Fonts stylesheet
  and embedded YouTube links opened from project modals.
