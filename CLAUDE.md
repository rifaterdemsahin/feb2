# CLAUDE.md - Project Instructions

## Project: Video Post Production Helper (Feb 2026)

Static site for video post-production workflows. No build system — plain HTML/CSS/JS served via Live Server (port 5502).

## 7-Phase Structure

```
1_Real_Unknown/   → OKRs and objectives
2_Environment/    → Roadmap, use cases, input files
3_Simulation/     → UI mockups
4_Formula/        → Guides and algorithms
5_Symbols/        → Core source code (main app lives here)
6_Semblance/      → Error logs and debugging
7_Testing_known/  → Validation and test plans
```

## Key Files

- `5_Symbols/postproduction_helper.html` — Main app (8 tabs)
- `5_Symbols/timeline.html` — Artifact timeline with copy-to-clipboard + toast
- `5_Symbols/file_inventory.html` — Asset inventory (search, sort, tags)
- `5_Symbols/video_editing_plan_ready.html` — Editing workflow planner
- `5_Symbols/markdown_renderer.html` — Markdown doc viewer (uses marked.js CDN)
- `5_Symbols/nav_5symbols.html` — Shared nav component (fetched via JS)
- `index.html` — Landing page

## Conventions

- Each page in 5_Symbols fetches `nav_5symbols.html` and sets its own active link
- Each page must include `.top-nav` CSS styles locally (no shared stylesheet)
- Copy-to-clipboard uses silent toast notifications (bottom-right), never alert()
- All pages are self-contained HTML — no bundler, no npm, no framework
- Uses PrismJS and js-yaml from CDN where needed

## Local Services

- **Live Server**: http://127.0.0.1:5502
- **Ollama**: http://localhost:11434 (model: nomic-embed-text, dim: 1536)
- **Qdrant**: http://localhost:6333 (API key in .env)

## Deploy

GitHub Pages: https://rifaterdemsahin.github.io/feb2/
