# README.md

## AS\_352 Swine Production — Flashcard Quiz

Single‑file web app for practicing questions from **AS\_352 Swine Production**. It loads a verified JSON dataset and gives instant ✅/❌ feedback, auto‑next on correct, progress tracking, and a review screen.

### Live locally

```bash
# Option 1: simple file open
# Double‑click index.html (works in most browsers)

# Option 2: serve locally (prevents some fetch/cache issues)
python3 -m http.server 8080
# then open http://localhost:8080
```

### Deploy to GitHub Pages

1. Create a repo, e.g. `as352-flashcards`.
2. Place these files in the repo root:

   * `index.html` (the app)
   * `as352_verified_qna_FINAL.json` (the dataset)
3. Commit & push.
4. In repo **Settings → Pages**: set **Source** to your default branch (e.g. `main`) and **/root**.
5. Open the Pages URL.

> If the dataset file isn’t present, click **Import JSON** in the app to load a local file.

### Dataset format

The app expects an array of objects:

```json
{
  "question": "…",
  "options": ["A", "B", "C", "D"],
  "answer": 0,
  "answer_text": "A",
  "support_1": "optional short snippet",
  "support_2": "optional short snippet"
}
```

### Customization tips

* **Shuffle**: toggle in the UI.
* **Auto‑next**: toggle in the UI.
* **Sounds**: lightweight base64 stub included; replace with your own short WAVs if you want.
* **Styling**: Tailwind via CDN; tweak colors in `:root` inside `<style>` block.

### Files

```
/ (repo root)
├─ index.html
├─ as352_verified_qna_FINAL.json
└─ README.md
```

---

## as352\_verified\_qna\_FINAL.json (placeholder)

Use this tiny sample to confirm your hosting works. Replace it with your full verified dataset.

```json
[
  {
    "number": 1,
    "question": "A farmer notices imported pigs with very large litters and heavy milk production. Which breed is this?",
    "options": ["Landrace","Duroc","Hampshire","Large White"],
    "answer": 3,
    "answer_text": "Large White",
    "support_1": "Large White: large litters with heavy milk production.",
    "support_2": ""
  },
  {
    "number": 2,
    "question": "Which breed has high lean meat yield but is PSE‑prone?",
    "options": ["Berkshire","Chester White","Pietrain","Tamworth"],
    "answer": 2,
    "answer_text": "Pietrain",
    "support_1": "Pietrain: extremely high lean to fat; PSE prone.",
    "support_2": ""
  }
]
```

> After you confirm the app loads this placeholder, overwrite it with your full `as352_verified_qna_FINAL.json` (the verified 247‑item file you downloaded).

---

## Troubleshooting

* **Blank page or dataset not loading**: ensure `as352_verified_qna_FINAL.json` sits **next to** `index.html` in the same folder, or use the **Import JSON** button.
* **CORS/fetch errors on file://**: run a local server (see `python3 -m http.server 8080`).
* **GitHub Pages cache**: hard refresh (Shift+Reload) or append `?v=2` to the page URL.
