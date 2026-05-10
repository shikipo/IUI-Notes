# Milestone 1: Concept Development
## Project: Interactive Foreign Language Reader

---

## 1. Design Challenge

> **"How might we help language learners understand unfamiliar words while reading, without interrupting their natural reading flow?"**

---

## 2. Personas

### Persona A — The Academic Reader
**Name:** Anna, 26  
**Background:** PhD student in biology. Regularly needs to read research papers in English, which is not her native language.  
**Problem:** She knows most academic vocabulary but stumbles on specific technical terms. Opening a dictionary tab costs focus and time.  
**Tech comfort:** Medium. Mainly uses a laptop or tablet.

---

### Persona B — The Comic Enthusiast
**Name:** Lucas, 22  
**Background:** Graphic design student, huge manga/comic fan. Wants to read Japanese manga and German bandes dessinées in their original language to get the authentic experience.  
**Problem:** Switching between the comic and Google Translate every few panels completely breaks immersion. He ends up reading in translation anyway.  
**Tech comfort:** High. Uses laptop and phone.

---

## 3. Storyboard — Main Scenario (Lucas)

> *(Each frame = one storyboard panel. Keep sketches simple.)*

**Frame 1:** Lucas finds a German comic he wants to read. He opens the web app.

**Frame 2:** He uploads the PDF/image of the comic page. A loading indicator appears: *"Analysing text…"*

**Frame 3:** The same comic page is displayed in the browser — visually identical — but words are now interactive (subtle highlight on hover).

**Frame 4:** Lucas reads comfortably. He doesn't know the word *"épuisé"*. He hovers over it (or taps on mobile).

**Frame 5:** A small, clean popup appears next to the word: *"épuisé → exhausted"* — and disappears when he moves on.

**Frame 6:** Lucas finishes the page without ever leaving the app. He feels immersed. He saves a few unknown words to his vocabulary list.

---

## 4. Features

### Must-Have
- Upload a PDF or image file in the browser
- OCR / text recognition to detect words and their positions on the page
- Render the original document visually, with words overlaid as interactive elements
- On hover (desktop) / on tap (mobile): show word translation via Dictionary API
- Basic support for one language pair (e.g. German → English, English → German)

### Nice-to-Have
- Vocabulary list: save words looked up during a session
- Support for multiple source languages
- Confidence score display (for OCR quality)
- Highlight words the user has looked up before
- Export vocabulary list as CSV (e.g. for Anki import)
- Word learning progress tracking (collecting data on which words are looked up most often, etc.; passive feature = require user input but could be used for future repetition features)
- Weekly vocabulary quiz (based on previous feature; active, requires user input)

---

## 5. IUI Concepts

### IUI Goal
**Effectiveness** — the user completes reading comprehension with less friction and fewer interruptions than traditional workflows (tab-switching, manual lookup).

### IUI Area
- **Analysis of input** — OCR/ML processes the uploaded document to extract and locate words
- **Generation** — the system generates an interactive overlay on top of the original content

### Key Achievements (from project requirements)
1. **Novel input modality** — the user interacts with a rendered document directly; hovering over detected text regions is a non-standard interaction pattern tied to ML-processed output
2. **Integrating an ML model** — OCR (e.g. Tesseract.js or Google Vision API) performs text recognition and spatial localisation
3. **Integrating an external API** — Dictionary/Translation API (e.g. MyMemory, LibreTranslate, or Free Dictionary API) provides the translation on demand
4. (Optional) **User modelling** — saving looked-up words to a vocabulary list, tracking which words are most frequently looked up, etc. Cant be implemented as a passive feature (data collection only; _how much words are looked up in this week, which words are most frequently looked up_) but could be used for future active features (quizzes, spaced repetition, etc.)

---

## 6. Prototype Screens (Mockup Description)

### Screen 1 — Upload View
- Clean centered layout
- Drag-and-drop zone: *"Drop your PDF or image here"*
- Supported formats listed below: PDF, PNG, JPG
- Language selector: *"Document language: [German ▾]"*
- Button: *"Start Reading"*

### Screen 2 — Reading View (Desktop)
- Document page rendered full-width
- Words subtly underlined or highlighted on hover only (not permanently, to preserve visual fidelity)
- On hover: small floating card appears near the word
  - Word (original)
  - Translation
  - Optional: phonetic / part of speech
- Top bar: page navigation, zoom, language toggle
- Side panel (optional): saved vocabulary list

### Screen 3 — Reading View (Mobile)
- Same document rendered, scrollable
- Tap on word → bottom sheet slides up with translation
- "Save word" button in the bottom sheet
- Clean, minimal UI — document takes full screen

---

## 7. Tech Stack (for reference)

| Component | Technology |
|---|---|
| Frontend | React + TypeScript |
| OCR / Text detection | Tesseract.js (browser-side) or Google Vision API |
| Translation | MyMemory API / Free Dictionary API |
| PDF rendering | PDF.js |
| Styling | TailwindCSS |

---

## Submission Checklist
- [ ] Slides prepared (PDF export)
- [ ] Mockup screens included in slides
- [ ] All team member names on title slide
- [ ] Submitted as .zip via e-Learning before 20./21.05.
