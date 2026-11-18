# plecoroundup
This is a tool that will allow Mandarin students to quickly save phrases into pleco flashcard format, and export to a file.

## Pleco Phrase Catcher

The live tool is hosted as a private claude.ai page:
https://claude.ai/artifact/KqCEQ3ZENgwUqwmWYAVeSW

`index.html` is the source of that page, kept here as a backup.

### What it does
- **Capture:** paste many phrases at once. The parser accepts one phrase per line (fields split by `|`, tab, ` - ` or `=`), lines with no separator (`谢谢 xièxie thank you`), or blocks of 2–3 lines separated by a blank line.
- **Fill gaps:** pinyin is generated from the characters (pinyin-pro). Cards still missing characters, pinyin or English can be filled with Claude.
- **Export:** writes a Pleco plain-text import file: an optional `//Category` line, then one card per line as `characters<TAB>pinyin<TAB>English`. In Pleco: Flashcards → Import / Export → Import Cards.
- **Clear:** after importing, delete exported cards to start a fresh batch.

### Runtime notes
The page uses claude.ai artifact capabilities: `db` + `user` (deck synced to your account), `sample` (Fill with Claude) and `downloads` (saving the file). Opened anywhere else, it falls back to saving cards in the browser's local storage, hides Fill with Claude, and shows the export text to copy instead of saving a file. A self-hosted version would need its own storage, translation backend and a plain download link.

### Updating the live page
Edit `index.html`, then republish it to the same claude.ai address from a Claude Code session (Artifact publish with `url` set to the address above).
