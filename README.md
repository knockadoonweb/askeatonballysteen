# Askeaton & Ballysteen Parish Website

A static website for Askeaton and Ballysteen Parish, Diocese of Limerick, Ireland.

## Hosting on GitHub Pages

1. Create a new GitHub repository (e.g. `askeaton-parish`)
2. Upload all files from this folder into the repository
3. Go to **Settings → Pages → Source → Deploy from branch: main**, folder: `/ (root)`
4. Your site will be live at `https://yourusername.github.io/askeaton-parish/`

---

## File Structure

```
/
├── index.html          ← Home page
├── masses.html         ← Mass times & services
├── news.html           ← Parish news (blog-style)
├── history.html        ← Parish history & timeline
├── safeguarding.html   ← Child & vulnerable adult protection
├── contact.html        ← Contact form & maps
├── style.css           ← Shared stylesheet
├── nav.js              ← Shared header & footer (injected)
├── liturgy.js          ← Liturgical calendar calculator
├── data/
│   └── news.json       ← ⭐ EDIT THIS FILE to add/remove news posts
└── images/
    ├── parish_crest.png    ← St. Mary's Parish full crest logo
    ├── logo_coloured.png   ← AM gothic window logo (coloured)
    └── logo_white.png      ← White version logo (for dark backgrounds)
```

---

## 📝 How to Add News (No coding required!)

Open the file `data/news.json` in any text editor (Notepad, TextEdit, etc.)

Each post looks like this:

```json
{
  "id": "6",
  "title": "Your Headline Here",
  "date": "2025-08-10",
  "category": "Parish News",
  "excerpt": "A short summary shown on the home page (1–2 sentences).",
  "body": "The full text of the article. Write as much as you like.\n\nUse two backslash-n to create a paragraph break."
}
```

**Available categories:** `Parish News`, `Events`, `Sacraments`, `Upcoming`, `Notices`

**To add a post:** Copy an existing block, paste it at the TOP of the list (after the `[`), give it a new `"id"`, fill in the details, and add a comma after the `}` before the next post.

**To remove a post:** Delete the entire `{ … }` block (and the comma before/after it).

**To publish changes:** Save the file and commit/push to GitHub. Changes appear immediately.

---

## 📬 Contact Form Setup (Optional)

The contact form uses [Formspree](https://formspree.io) (free plan: 50 messages/month).

1. Create a free account at https://formspree.io
2. Create a new form and copy your Form ID (looks like `xyzabc12`)
3. In `contact.html`, find the line:
   ```html
   <form id="contactForm" action="https://formspree.io/f/YOUR_FORM_ID" method="POST"
   ```
4. Replace `YOUR_FORM_ID` with your actual ID.

Without this step, the form will not send emails — but the rest of the website works fine.

---

## 🗺️ Google Maps

The maps in `contact.html` use embedded Google Maps iframes. They should work without an API key for basic embedding.

If you need to update the map pins (e.g. for more precise locations), you can:
1. Go to [maps.google.com](https://maps.google.com)
2. Search for the church
3. Click Share → Embed a map → Copy the iframe code
4. Replace the existing `<iframe ...>` in `contact.html`

---

## ✟ Liturgical Calendar

The calendar (`liturgy.js`) is entirely self-contained — it computes the liturgical season and feast days automatically from today's date with no external API or internet connection required. It covers:

- All liturgical seasons (Advent, Christmas, Lent, Easter, Ordinary Time)
- All major Solemnities, Feasts, and Memorials of the Roman Rite
- Moveable feasts (Easter, Ash Wednesday, Pentecost, etc.)
- St Patrick's Day as a Solemnity (Irish observance)

The calendar updates automatically every day with no maintenance needed.

---

## 🎨 Customisation

- **Colours:** Edit the CSS variables at the top of `style.css` (`:root { ... }`)
- **Mass Times:** Edit `masses.html` directly
- **Parish History:** Edit `history.html` directly
- **Safeguarding contacts:** Edit `safeguarding.html` directly

---

*Website maintained by the Parish Office. For technical queries, contact the Diocese of Limerick.*
