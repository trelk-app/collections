# Trelk Community Collections

Curated reading collections for the [Trelk](https://trelk.app) personal knowledge engine.

Browse, import, and contribute reading lists on any topic — from "Top AI Research Papers" to "Best Resources to Learn Python." Every collection can be imported into Trelk with a single tap, where each item gets summarized, tagged, embedded, and connected to your personal knowledge graph.

## What is this?

This repository hosts community-maintained collections of articles, papers, videos, and documentation that Trelk users can browse and import directly from inside the app. Each collection is a curated reading list on a specific topic.

The Trelk app fetches collections from this repo at runtime — no app updates needed when new collections are added.

## How to import a collection

1. Open Trelk on your phone or tablet
2. Go to **Settings → Community Collections**
3. Browse the available collections, tap one to preview its items
4. Tap **Import** — every item gets processed by on-device AI: summarized, tagged, embedded, and added to your library

## Repository structure

```
.
├── index.json              # Master list of all collections (metadata only)
└── collections/
    ├── ai-papers-2025.json
    ├── learn-python.json
    └── ...                 # One file per collection
```

## How to contribute a collection

Want to share your own reading list? We'd love to have it.

### Option 1: Open a Pull Request

1. Fork this repo
2. Create a new file at `collections/your-collection-slug.json` using the format below
3. Add an entry for your collection in `index.json`
4. Open a PR

### Option 2: Export from the Trelk app

1. In Trelk, build a collection of items you want to share
2. Go to **Settings → Community Collections → Submit Collection**
3. The app generates the JSON and opens a pre-filled GitHub issue — just review and submit

## Collection format

### `index.json` (master list)

```json
{
  "version": 1,
  "updatedAt": "2026-04-10T00:00:00Z",
  "collections": [
    {
      "slug": "learn-python",
      "name": "Best Resources to Learn Python",
      "description": "Curated tutorials, docs, videos, and repos for learning Python — beginner to advanced.",
      "author": "your-github-username",
      "itemCount": 20,
      "tags": ["python", "programming", "learning"],
      "icon": "code-slash-outline",
      "updatedAt": "2026-04-10T00:00:00Z"
    }
  ]
}
```

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `slug` | string | yes | Unique identifier — must match the filename in `collections/` |
| `name` | string | yes | Display name |
| `description` | string | yes | Long-form description |
| `author` | string | yes | Your name or GitHub handle |
| `itemCount` | number | yes | Total items in the collection |
| `tags` | string[] | yes | Topic tags for filtering |
| `icon` | string | yes | Ionicons name (see below) |
| `updatedAt` | string | yes | ISO 8601 timestamp |

### `collections/{slug}.json` (individual collection)

```json
{
  "name": "Best Resources to Learn Python",
  "description": "Curated tutorials, docs, videos, and repos for learning Python.",
  "author": "your-github-username",
  "items": [
    {
      "url": "https://docs.python.org/3/tutorial/index.html",
      "title": "The Official Python Tutorial",
      "summary": "The official Python documentation tutorial. Covers data structures, modules, I/O, and error handling.",
      "content_type": "documentation",
      "tags": ["beginner", "official", "tutorial"],
      "language": "en"
    },
    {
      "url": "https://www.youtube.com/watch?v=rfscVS0vtbw",
      "title": "Learn Python — Full Course for Beginners",
      "summary": "A 4.5-hour comprehensive Python course by freeCodeCamp.",
      "content_type": "video",
      "tags": ["beginner", "video", "free"],
      "language": "en"
    }
  ]
}
```

### Item fields

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `url` | string | **yes** | Full URL to the resource |
| `title` | string | **yes** | Display title |
| `summary` | string | no | Brief description (1-3 sentences) |
| `content_type` | string | no | One of: `article`, `paper`, `documentation`, `video`, `newsletter`, `note` |
| `tags` | string[] | no | Topic tags |
| `language` | string | no | ISO 639-1 code, defaults to `en` |

### Icons

Use any [Ionicons](https://ionic.io/ionicons) name (without size prefix). Good options for collections:

- `flask-outline` — research, science
- `code-slash-outline` — programming
- `book-outline` — books, literature
- `school-outline` — education
- `globe-outline` — general / web
- `bulb-outline` — ideas, productivity
- `library-outline` — reference
- `briefcase-outline` — business

## Quality guidelines

- **Curate, don't dump.** Every item should genuinely belong in the collection.
- **Add summaries.** They make the collection scannable and help users decide what to read first.
- **Use accurate tags.** Tags help users filter and discover.
- **Respect copyright.** Only link to publicly accessible resources.
- **Keep it focused.** A collection should have a clear theme. Split broad topics into multiple collections.

## License

All collections in this repository are released under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — free to use, share, and adapt with attribution.

The links themselves point to third-party content owned by their respective creators.

## Get Trelk

- **iOS:** [App Store](https://apps.apple.com/us/app/trelk-read-think-connect/id6761143849)
- **Android:** Coming soon
- **Website:** [trelk.app](https://trelk.app)
