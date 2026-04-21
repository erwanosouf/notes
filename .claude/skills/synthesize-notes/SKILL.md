---
name: synthesize-notes
description: >
  Synthesize raw notes and photos from a conference talk, training, or video
  into a structured markdown file. Use when the user provides raw notes,
  images, or a document to organize into the repository.
allowed-tools: Read Glob Bash Write Edit
argument-hint: [event|training|video|article]
---

You will be provided with raw notes, photographs, or a document from a conference talk, training session, video, or article — along with optional context (event link, speaker names, date).

Your goal is to reorganize and synthesize this into a clean markdown file that fits this repository's conventions.

## Step 1: Determine note type and metadata

From `$ARGUMENTS` or user context, determine:
- **Type**: `event`, `training`, `video`, or `article` — this decides the target directory
- **Date**: in `YYYY-MM-DD` format (or `YYYY-MM` for month-scoped notes like video batches). This is the date the **source event actually took place** (talk day, training day, article publication, video release) — **never** the date the notes were written or synthesized. If the source doesn't make the event date obvious, determine it from the event page / blog / conference schedule before choosing the filename; if still unclear, ask the user rather than defaulting to today.
- **Title**: short descriptive name using underscores (e.g., `Devoxx_Day1`, `Arolla_DDD`)
- **Language**: match the source material — French or English

Target directories:
| Type | Directory |
|------|-----------|
| event | `events/` |
| training | `trainings/` |
| video | `videos/` |
| article | `articles/` |

File naming: `<directory>/<YYYY-MM-DD>_<Title>.md` (or `<YYYY-MM>_<Title>.md`)

## Step 2: Process images

Read all provided images using the Read tool.

- **Photo of slides or handwritten notes whose value is purely textual** (bullet lists, titles, quotes, reading content off the screen): extract the text and integrate it into the notes. **Do not** save these photos to `assets/` or embed them — the transcription replaces them entirely.
- **Diagrams, schemas, charts, sketches, or other visual artifacts that lose meaning if transcribed to text**: copy them to `assets/` with a descriptive filename and embed them as `![Description](../assets/filename.ext)`.

Rule of thumb: if you can losslessly convert the image to a bulleted list or a blockquote, it's textual — don't keep the file. Only keep images that carry information the text cannot (spatial layout, visual metaphor, a drawing).

### Extracting images embedded in a Google Doc

⚠️ `mcp__claude_ai_Google_Drive__read_file_content` returns **text only** — embedded photos are silently dropped. Before synthesizing from a Google Doc, compare the file size in `get_file_metadata` with the text length: if the file is much larger than the text warrants (e.g. 800KB for 1KB of typed notes), there are embedded images you haven't seen.

To recover them, export the doc as a zip (HTML + `images/`):

1. Call `mcp__claude_ai_Google_Drive__download_file_content` with `exportMimeType: application/zip`. The response is a base64 blob; for any non-trivial doc it will exceed the tool-result token limit and land in a `tool-results/…txt` file on disk.
2. Decode and unpack it:
   ```bash
   cd /tmp && mkdir -p gdoc_extract && cd gdoc_extract && python3 -c "
   import json, base64
   with open('<path-to-tool-results-file>') as f:
       data = json.load(f)
   raw = base64.b64decode(data['content'][0]['embeddedResource']['contents']['blob'])
   open('doc.zip', 'wb').write(raw)
   " && unzip -o doc.zip > /dev/null && ls images/
   ```
3. Read the exported `.html` file — the `<img src="images/imageN.jpg">` order is the document display order, which is **not** the numeric filename order (Google reuses indices as images are edited/moved). Read images in HTML order so your synthesis follows the slide sequence the user actually saw.

## Step 3: Produce the structured markdown file

Follow this structure:

### H1 — Main title
The event name, training title, or video title.

### Talk/session sections (H2)
For events with multiple talks, each talk gets an H2:
```markdown
## Talk Title

*Speaker Name (Organization)*
```

Use H3/H4 for subsections within a talk.

### Content formatting conventions
- Bullet points (`-`) for key concepts and notes
- `💡 ...` for important takeaways (just the lightbulb, no "Key Takeaway" label)
- `⭐` to `⭐⭐⭐` on H2 titles to rate talks (only if the user provides ratings)
- `⚠️` for warnings or caveats
- `➕` / `➖` for pros/cons
- `>` blockquotes for direct quotes or definitions
- Tables for structured comparisons
- Inline links for slides, videos, specs: `[Slides](URL)`, `[YouTube](URL)`

### References section (required)
Add a `## References` section at the end containing all mentioned:
- **Books** (title, author)
- **People** (name, role/org if known)
- **Articles and blog posts** (with links)
- **Tools and libraries** (with links)
- **Principles and concepts** (name, brief description)

Use reference-style links at the bottom of the file when there are many URLs:
```markdown
[label]: https://example.com
```

## Step 4: Write the file

Use the Write tool to create the file at the determined path.

## Step 5: Update README.md

Read `README.md` and add a link to the new file under the appropriate section:
- Events/trainings go under `## Events and Trainings`
- Articles go under `## Articles`
- Videos: add a `## Videos` section if it doesn't exist

Format: `- [Display Name (YYYY-MM-DD)](path/to/file.md)`

Maintain chronological order within each section.

## Step 6: Confirm

Tell the user:
- The file path created
- A brief summary of what was synthesized
- Any images saved to `assets/`
- Whether README.md was updated
