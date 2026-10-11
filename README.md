# Wordloom — GRE vocabulary studio

A buildless, browser-only site for GitHub Pages. No API keys or installation needed.

## Publish on GitHub Pages
1. Create a GitHub repository (for example `gre-word-lab`).
2. Upload **the contents of this folder** into the repository root: `index.html`, `style.css`, `app.js`, `data.js`, and `.nojekyll`.
3. In the repository, open **Settings → Pages**. Under Build and deployment, choose **Deploy from a branch**, select **main** and **/(root)**, then Save.
4. Open the Pages URL shown there when deployment finishes. A project site usually uses `https://YOUR-USERNAME.github.io/gre-word-lab/`.

For a local preview, run `python3 -m http.server 8080` inside this folder and open `http://localhost:8080`.

## Practice
Eight modes: mixed practice, definition choice, reverse definition, synonym choice, two-answer synonyms, typed recall, double-duty contrasts, and self-rated flashcards. Sessions contain ten questions. Use the word collection and group filters to focus. ETS priority selects matched study headwords with source frequencies of at least three.

Answers receive immediate explanations. Misses are due after five minutes; correct streaks schedule review after 1, 3, 7, 14, then 30 days. Missed words also remain in the review collection until answered correctly. All progress, bookmarks, and personal memory hooks stay in browser localStorage. Export/import JSON backups in My progress to move devices. Clearing browser data removes saved progress.

## Content and scope
Extracted from the user's three PDFs:
- `_Easy_ words that do double-duty - Google Sheets.pdf`: 47 familiar/GRE meaning pairs.
- `Synonyms_Gregmat - Google Sheets.pdf`: synonym study headwords and associated terms, organized by source group.
- `All_ETS_Material_TC - Google Sheets.pdf`: 5,012 frequency rows (word forms/families), searchable in the library and used to prioritize matching headwords.

There are 3,006 unique practice terms: 852 imported headwords and 2,154 additional associated synonym terms. Definition questions use the explicitly defined double-duty entries. The synonym source supplies associations, not formal definitions: some are loose, sense-dependent, or contain source typos. Synonym questions explicitly ask about source-listed terms. These are generated vocabulary drills, not official ETS questions or a replacement for full GRE sentence-equivalence/text-completion exercises. The frequency-only entries are references, not unsupported definition quizzes.

The source PDFs are not bundled. If you publish publicly, ensure you have permission to redistribute the vocabulary compilation. No analytics, accounts, or server storage. Google Fonts is optional; fallback fonts work without it.

## Randomness with exhaustive repetition

The default collection is **Full synonyms — main words first**. Each pass covers all 817 imported main synonym headwords first, followed by 2,154 additional associated terms. Terms shared with the headword list are not duplicated. Associated-term questions ask which main headwords list that term; they do not treat those headings as formal definitions. Choose Main synonym headwords for a focused pass or All practice vocabulary to include the remaining double-duty words.

- Each deck/group/practice-mode selection has a saved coverage pass. Words are chosen randomly from the unanswered headwords in that pass. A word counts as covered only after you answer it.
- Every eligible headword gets one coverage turn before the next pass begins. The next pass randomizes the order again; ten-question sessions do not reset coverage. Reloading the page also preserves completed coverage.
- Every fourth answer slot can bring back a missed word, after at least three intervening answers. These extra reviews do not consume coverage turns, so weak words cannot prevent the rest from appearing.
- With Full synonyms or All practice vocabulary selected, synonym headwords come first in each pass, followed by the associated terms and other eligible words.
- Mixed practice chooses a headword first, then selects one of its least-practiced eligible question types. Synonym choices rotate through that headword's associated terms rather than repeatedly drawing the same synonym.
- The practice footer shows pass number, covered words, and remaining words. My progress shows lifetime coverage of the main headwords. Export/import preserves coverage passes too. Old backups without coverage start a new pass while retaining word progress.

Coverage always refers to the selected eligible set: definition-only practice cannot quiz headwords without supplied definitions. Frequency-only ETS rows remain reference entries.

## Import counts
852 distinct imported headwords; 817 have synonym associations. Cleaning parenthetical annotations and excluding prose fragments leaves 2,154 additional synonym terms, for 3,006 total practice terms. ETS contributes 5,012 reference rows and 6,345 distinct word forms, many overlapping the practice vocabulary. Those forms are not automatically assigned invented definitions. Source typos and loose associations may remain.
