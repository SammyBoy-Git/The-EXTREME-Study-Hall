# The Extreme Study Hall

A single-file, browser-based study site for practice in **Reading**, **Social Studies**, and **Math**. It is designed as a boot camp for prep tests, with practice questions, worked examples, flashcard decks, strategy cheat sheets, XP, and streak tracking.

Everything lives in one HTML file, `The_Extreme_Study_Hall.html`. No install, build step, or server is required.

## Quick Start

1. Download `The_Extreme_Study_Hall.html`.
2. Open it in any modern desktop or mobile browser.
3. Pick a subject from the top tabs and start practicing.

An internet connection is needed on first load so the page can fetch its fonts (Google Fonts) and the Tailwind CSS script (`cdn.tailwindcss.com`). Progress is saved in your browser's local storage, so it stays on that browser and device.

## Subjects

The top bar switches between three study halls. Each one runs in its own embedded frame.

### 📚 Reading
**The Reading Study Hall: Extreme Prep Edition**

- **Practice Arena:** eight reading categories, each with its own practice bank:
  - Vocabulary & Context
  - Greek & Latin Roots
  - Figurative Language
  - Main Idea & Details
  - Inference & Conclusions
  - Cause & Effect / Structure
  - Author's Purpose & Tone
  - Grammar & Mechanics
- **Ultimate Reading Study Hub:** a "Get the Jist" quiz, 250 worked examples, and a Vocabulary track.
- **Flashcards & Cheat Sheet:** 250-card decks per category, plus a Reading Strategy Cheat Sheet.

### 🌍 Social Studies
**The Social Studies Study Hall: Extreme Prep Edition**

- **Practice Arena (250 Practice Tests):** eight topic areas:
  - U.S. Geography & Maps
  - World Geography
  - Colonies to Revolution
  - Constitution & Expansion
  - U.S. Government & Civics
  - Economics & Finance
  - Ancient Civilizations
  - Historical Thinking
- **Ultimate Study Hub:** a "U.S. Geography" quiz, 250 worked examples, and a map-skills section.
- **250 Flashcards & Vault:** decks per topic, plus a Strategy & Reference Cheat Sheet Vault.

### ➗ Math
**The Math Study Hall: Extreme Prep Edition**

- **Practice Arena:** targeted tracks for:
  - Addition
  - Subtraction
  - Multiplication
  - Division
  - Square Roots
  - Exponents & Powers
  - Order of Operations (PEMDAS)
  - Advanced & Fractions/Decimals
- **Ultimate Study Hub:** a "Multiplication" quiz and 250 step-by-step worked examples.
- **Strategy Vault & Flashcards:** flashcard decks and strategy notes per topic.

## Features

- **Practice Arena:** questions by topic, with answer checking. A **Rush Mode** timer is available on the practice screens.
- **Diagnostic:** a 25-question diagnostic ("Start 25-Q Diagnostic") to gauge readiness across a subject.
- **Flashcards:** flip cards with tips, shuffle, next/previous, and random navigation. Mark cards as **Mastered** and filter to **Needs Review**.
- **Cheat Sheets:** strategy and reference content in each Vault.
- **Progress tracking:** XP stars, daily streak, and a Prep Readiness score per subject.
- **Reset:** the **Reset** button in the header clears all saved progress after a confirmation prompt. Each subject also has its own reset option.

## Saved Data

Progress is stored with the browser's `localStorage` (XP, streaks, mastered flashcards, and readiness scores). Clearing site data or using a different browser or device starts over from zero. Use **Reset** to clear progress deliberately.

## Browser Support

Any current version of Chrome, Edge, Firefox, Safari, or their mobile equivalents. The layout adjusts for phones: the study frames resize on screens 640px wide or less.

## Project Structure

```
The_Extreme_Study_Hall.html   # The whole app: layout, styles, and all three study halls
```

Each subject is embedded as an `<iframe>` with `srcdoc`, and the top-level page switches between them with a small `show()` function. Each frame has its own script class (`StudyHallExtreme`, `MathStudyHallExtreme`, and so on) that manages its questions, flashcards, and saved state.

## Customizing

Because everything is in one file, you can edit it in any text editor:

- **Questions and decks** live in JavaScript arrays inside each frame (for example `vocabBank`, `mainIdeaBank`, `coloniesData`, `addition` question lists, and `fcList` flashcard lists).
- **Colors and styles** are in the `<style>` block at the top of each frame and in Tailwind utility classes.
- **Branding** (titles and the "EXTREME PREP" badge) is in the header markup of each frame.

To keep changes isolated, back up the file before editing. Remember that the frames are stored as escaped `srcdoc` attributes in the outer file, so edits to the inner code need to be escaped (or made in a copy of each subject's HTML and then re-embedded).

## Notes and Limitations

- The app is a study aid. It does not connect to any official test or score report.
- External resources (Google Fonts, Tailwind CSS CDN) need network access for the intended styling. Without them, the page falls back to system fonts and may look plainer.
- Progress is local only. There is no account system or cloud sync.

## Credits

Built as a self-contained practice site. Tailwind CSS is loaded from its CDN, and fonts are from Google Fonts (Inter, Fredoka, and Space Grotesk).
