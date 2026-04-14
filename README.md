# Markdown stduio

Production-grade hybrid Markdown editor inspired by Notion and VS Code workflows.

## Highlights

- Hybrid editing engine:
	- Rich text editing with TipTap
	- Raw Markdown editing with CodeMirror
	- Live preview with secure markdown-it pipeline
- Loss-aware conversion flow:
	- Markdown -> Rich (rendered HTML)
	- Rich -> Markdown (Turndown + GFM rules)
- CommonMark + GFM support with extended syntax:
	- Headings, links, references, nested lists, task lists, blockquotes
	- Tables with alignment
	- Footnotes, definition lists, abbreviations
	- Highlight, subscript, superscript, keyboard tags
	- Math (KaTeX), Mermaid, safe inline HTML, details/summary
- UX features:
	- Split/editor/preview layouts
	- Sticky toolbar + formatting actions
	- Slash command menu
	- Keyboard shortcuts
	- Outline sidebar + live stats
- Storage and export:
	- Debounced auto-save to localStorage
	- Manual save
	- Export as .md, .html, .pdf (print flow)
- Performance and security:
	- Large-document preview guard + sectioned rendering
	- Debounced updates
	- Sanitized rendering pipeline with DOMPurify

## Stack

- React + Vite
- TipTap (rich editor)
- CodeMirror (raw markdown editor)
- markdown-it + plugins (preview rendering)
- Turndown + GFM plugin (rich-to-markdown conversion)
- Zustand (state management)
- Tailwind CSS v4 (+ Typography plugin)

## Folder Structure

```text
src/
	components/
		EditorLayout.jsx
		MarkdownPreview.jsx
		ModeSwitchers.jsx
		OutlineSidebar.jsx
		RawMarkdownEditor.jsx
		RichTextEditor.jsx
		SlashCommandMenu.jsx
		StatsBar.jsx
		Toolbar.jsx
	editor/
		defaultDocument.js
		markdownPipeline.js
	hooks/
		useAutosave.js
		useDebouncedCallback.js
		useDocumentStats.js
		useKeyboardShortcuts.js
	store/
		editorStore.js
	utils/
		exporters.js
```

## Development

```bash
npm install
npm run dev
```

## Production Build

```bash
npm run lint
npm run build
```

## Notes

- Mermaid is lazy-loaded in preview mode to reduce initial bundle impact.
- Preview rendering is sanitized before being mounted in the DOM.
- The rich-text engine supports core Markdown structures and round-trips through a configurable conversion layer for future schema extensions.
