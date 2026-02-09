# Gestalt Podcast — Episode Publishing Skill

## Purpose

This skill prepares a Gestalt Podcast episode for publishing across YouTube, Spotify, Apple Podcasts, Amazon Music, and Substack. It generates all required metadata in a single pass for efficient review.

## Required input

Before starting, verify that ALL of the following have been provided:

1. **Transcript** — SRT or timestamped transcript of the episode
2. **Episode length** — e.g., 38:42
3. **Examples file** — [references/podcast-description-examples.md](./references/podcast-description-examples.md)
4. **Resources & people** — list of resources and people mentioned in the episode (can be "none")
5. **B-roll credits** — names and links to B-roll footage authors (can be "none")

**If any input is missing, stop immediately. Do not generate anything. Ask for the missing items.**

## Workflow: 2-round batch process

### Round 1 — Generate everything

Produce a **single Markdown artifact** (canvas) containing all sections below, inline, so the host can scan and compare everything in one view.

The artifact must follow this exact structure:

---

```
# Episode Publishing Draft

---

## 🏷 TITLE OPTIONS (pick one)

1. <title>
2. <title>
3. <title>
4. <title>
5. <title>
6. <title>
7. <title>
8. <title>
9. <title>
10. <title>

---

## 💬 SUBTITLE OPTIONS (pick one)

1. <subtitle>
2. <subtitle>
3. <subtitle>
4. <subtitle>
5. <subtitle>
6. <subtitle>
7. <subtitle>
8. <subtitle>
9. <subtitle>
10. <subtitle>

---

## 📝 SHORT DESCRIPTION OPTIONS (pick one)

1. <short description>

2. <short description>

3. <short description>

4. <short description>

5. <short description>

6. <short description>

7. <short description>

8. <short description>

9. <short description>

10. <short description>

---

## 🎯 WHAT YOU'LL LEARN (review & adjust)

What you'll learn in this episode:
<emoji> <learning point>
<emoji> <learning point>
<emoji> <learning point>
<emoji> <learning point>
<emoji> <learning point>

---

## ✏️ CHAPTERS (review & adjust)

✏️ In This Episode:
00:00 - <chapter title>
MM:SS - <chapter title>
...

---

## 📚 RESOURCES AND PEOPLE MENTIONED

<resources and people, formatted per examples>

---

## 🔗 HOST LINKS

Find Nik Sumeiko online:
https://withnik.com
https://www.linkedin.com/in/niksumeiko/

Find Marius Bauer online:
https://www.linkedin.com/in/mariusbauer
https://konvergenz.studio

---

## 🎙 OTHER PLATFORMS

🎙 Gestalt Podcast (other platforms):
https://podcasts.apple.com/us/podcast/gestalt-podcast/id1764816250
https://open.spotify.com/show/4F1zpkO8VmfsfHzp6N4Ipz
https://music.amazon.de/podcasts/74852374-4378-428e-beaf-d4d6c02ca8cb/gestalt-podcast
https://gestaltpodcast.substack.com/s/gestalt-podcast

---

## 🎬 CREDITS

Hosts: Nik Sumeiko @niksumeiko, Marius Bauer
Editor: Joe Gustilo @dustyeditors (https://fiverr.com/producerelite)
Podcast art & background music: Marius Bauer (https://konvergenz.studio)
B-rolls: <names and links from input>

---

## 🔖 SEO TAGS (review & adjust)

<comma-separated tags>
```

---

### Round 2 — Selection and final output

The host responds with selections in a compact format, for example:

> "Title 3, Subtitle 7, Description 2. Learning points — drop bullet 3, rephrase bullet 1 to focus on X. Chapters: merge 3 and 4. Tags fine."

After receiving selections, produce the **final clean canvas** — a single Markdown artifact with only the chosen content, no numbered options, ready to copy-paste for publishing.

If the host requests further adjustments, iterate on the final canvas until confirmed.

### Round 3 — Examples file entry

Once the final canvas is confirmed, automatically generate a **separate copyable block** at the bottom of the canvas, under a heading `## 📋 COPY TO EXAMPLES FILE`. This block must be formatted **exactly** like the entries in [references/podcast-description-examples.md](./references/podcast-description-examples.md) — ready to copy-paste and append directly to that file.

The format (derived from existing examples):

```
---

### **<Selected title>**

<YouTube link>

<Selected subtitle>

<Selected short description>

What you'll learn in this episode:
<emoji> <learning point>
<emoji> <learning point>
...

✏️ In This Episode:
00:00 - <chapter>
MM:SS - <chapter>
...

Resources and people mentioned in the episode:
<resources, if any>

<comma-separated SEO tags>
```

Rules for this block:
- Start with `---` separator (matches the file's entry delimiter)
- Title in bold with `### **Title**`
- YouTube link placeholder (host will fill in the actual URL after upload)
- No host links, platform links, or credits — those aren't in the examples file
- Match the exact spacing and formatting patterns from existing entries

## Content generation rules

### Titles
- Study the tone and structure from [references/podcast-description-examples.md](./references/podcast-description-examples.md)
- Concise, compelling, title-case
- Mix of direct ("How to X"), declarative ("X Is Y"), and curiosity-driven ("The Truth About X") styles
- Target audience: digital creators, software developers, designers

### Subtitles
- One sentence, conversational tone
- Include 1–2 relevant emojis (see [references/podcast-description-examples.md](./references/podcast-description-examples.md) for style)
- Should complement the title, not repeat it

### Short descriptions
- 2–4 sentences max
- Mention @niksumeiko (Nik Sumeiko) and Marius Bauer by name
- If there's a guest, mention them with their handle and brief credential
- Focus on practical, results-oriented framing
- Use "In this episode" as the opening pattern (per [references/podcast-description-examples.md](./references/podcast-description-examples.md))

### What you'll learn
- 4–5 bullet points with emoji prefixes
- Each bullet: concise, action-oriented, specific
- Generate 1 variation initially; refine based on feedback

### Chapters

Role: You are a YouTube Chapter Generator. Analyze the provided transcript carefully, considering the episode topic, length, and selected title/subtitle/description to identify the most appropriate placement for each chapter.

Guidelines for identifying chapter boundaries:
1. Listen for natural pauses or transitions in the speaker's voice to identify when a new topic or section begins.
2. Pay close attention to the content being discussed and identify when the speaker moves from one main point to another.
3. If the speaker explicitly mentions a new topic or section, use that as a cue to place a timestamp.
4. Consider the overall flow of the episode and aim to place timestamps at intervals that make sense for the viewer — typically every 2–5 minutes for longer episodes, or at major topic shifts.
5. If the transcript includes visual cues or text overlays indicating a new section, use those as a guide for placing timestamps.

Formatting rules:
- Format: `MM:SS - Chapter title`
- Always start with `00:00 -` (intro or first topic)
- Chapter titles: short, descriptive, sentence case
- Typically 7–10 chapters for a ~38-minute episode
- Study chapter style and tone from [references/podcast-description-examples.md](./references/podcast-description-examples.md)

### SEO tags
- 15–25 comma-separated tags
- Mix of broad terms (e.g., "creator economy") and specific topics from the episode
- Include the podcast name: "gestalt podcast"
- Study tag patterns from [references/podcast-description-examples.md](./references/podcast-description-examples.md)

### Resources and people
- Format each resource with its type in parentheses: (book), (research), (report), (TV series), (tool), etc.
- People: Name with LinkedIn handle or relevant link
- Only include items explicitly provided in the input — never invent resources

### Credits and static sections
- Auto-fill from the template above — no creative input needed
- B-roll credits: use the names and links provided in the input
- If no B-rolls or resources are provided, omit those sections

## Branding rules

- Always use "in George" (not "at George") when referencing the George digital banking platform
- Emphasize practical, actionable guidance over theoretical concepts
- Highlight concrete results and measurable impact when relevant
- Keep language concise — initial drafts typically need condensing

## Post-publishing checklist

After the episode is published, complete these maintenance tasks:

- [ ] Copy the `📋 COPY TO EXAMPLES FILE` block from the final canvas and append it to [references/podcast-description-examples.md](./references/podcast-description-examples.md) in the GitHub repository (update the YouTube link placeholder with the actual URL)
- [ ] If the skill file was updated during this session, commit changes to the GitHub repository
- [ ] Copy the updated [references/podcast-description-examples.md](./references/podcast-description-examples.md) into the Claude Project
- [ ] If the skill file changed, update the Claude Project instructions to match
