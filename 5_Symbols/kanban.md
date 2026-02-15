# 5_Symbols - Code Kanban

## Done

- [x] **nav_5symbols.html** — Shared navigation component with links to all 5 pages + Home
- [x] **timeline.html** — Interactive artifact timeline with drag-scroll, filter buttons, 12 scenes, legend, stats, top-nav CSS fix applied
- [x] **file_inventory.html** — 4-tab inventory system (Overview, Full Inventory, Script Map, DaVinci Tags) with search, sort, copy-to-clipboard, 200+ assets
- [x] **markdown_renderer.html** — Sidebar markdown viewer loading project docs via marked.js CDN, with error handling for missing files
- [x] **video_editing_plan_ready.html** — Full interactive editing workflow: task sidebar, artifact browser modal, timeline controls, quality checklist, large data set
- [x] **postproduction_helper.html** — 8-tab post-production tool (Overview, Timeline, Shots, B-Roll, Graphics, Search, Checklist, Formula) with scene cards and smart search
- [x] **Top-nav consistency** — All 5 pages load `nav_5symbols.html` via fetch, set correct active link, and include `.top-nav` CSS

## In Progress

- [ ] **postproduction_helper.html — B-Roll filter/search** — `filterBRoll()` and `filterByCategory()` have `console.log` placeholders instead of actual DOM filtering logic (lines 1061, 1065)

## Backlog

- [ ] **Remove debug console.logs** — Clean up leftover `console.log` calls in postproduction_helper.html before production
- [ ] **Markdown renderer — verify all file paths** — Multiple markdown paths reference `../2_Environment/`, `../7_Testing_known/`, etc. — need to confirm all referenced `.md` files actually exist
- [ ] **Add error handling to nav fetch** — Nav fetch calls across all pages have no `.catch()` — a failed load silently leaves the nav empty
- [ ] **kanban.html** — No kanban board page exists yet; `kanban.md` is not linked from the nav
