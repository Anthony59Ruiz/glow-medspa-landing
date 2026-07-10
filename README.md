# Glow — Boutique Med Spa

A one-page website for **Glow**, a boutique med spa. It has one job: turn a curious visitor into a booked consultation.

**See it live:** https://anthony59ruiz.github.io/glow-medspa-landing/

---

## Who this is for

Anyone who wants to see, share, or make small edits to the Glow site — no technical background needed. If you can edit a document, you can change the words on this page.

## What the page does

A visitor scrolls through four sections, in this order:

1. **A warm welcome** — the spa's name, a single inviting line, and a button that takes you straight to the booking form.
2. **Three services** — Botox, facials, and laser treatments, each described by how it makes you feel rather than how it works clinically.
3. **Reassurance** — star ratings, real-sounding reviews, and a few numbers that build trust before anything is asked of the visitor.
4. **The booking form** — name, phone, email, and which service they're curious about.

Everything above the form exists to earn the form.

The page is designed to feel like a boutique spa, not a doctor's office: warm creams, soft gold, elegant type, lots of breathing room. It works on phones as well as laptops, and small touches fade in gently as you scroll.

## One important thing about the form

**Right now, the booking form doesn't send you anything.** A visitor can fill it out and they'll see a friendly thank-you message — but that information isn't emailed or saved anywhere. It simply disappears.

This is normal for a site that hasn't been fully connected yet. Before you share this link with real customers, someone will need to hook the form up to your email or booking system. The place to do that is already marked in the code, so it's a quick job for whoever helps you with this.

## How to view it

**The easy way:** click the live link above. That's the real site, and it updates automatically whenever changes are saved to the project.

**On your own computer**, if you want to preview changes before they go live: open the Terminal app, then type these two lines, pressing Enter after each.

```
cd ~/Desktop/glow-medspa-landing
python3 -m http.server 8000
```

Now open your web browser and go to **http://localhost:8000**. You'll see the page exactly as visitors would.

When you're finished, click back on the Terminal window and press `Control` + `C` to stop it.

## What's in here

You'll mostly care about the first one.

| File | What it is |
| --- | --- |
| `index.html` | All the words on the page. Edit here to change headlines, service descriptions, or reviews. |
| `styles.css` | The look — colors, fonts, spacing. |
| `script.js` | The behavior — checking the form is filled in correctly, and the gentle fade-in effects. |
| `glow-artifact.html` | A single-file copy of the whole page, handy for sharing as one attachment. |
| `CLAUDE.md` | Notes describing the site's intended look and feel. |

### A note on that copy

`glow-artifact.html` is a **separate copy** of the page, not a live mirror of it. If you change the wording in `index.html`, the copy won't update on its own — it has to be rebuilt. If the two ever disagree, trust `index.html`; that's the one the live site is built from.

## Making a change

Open `index.html` in any text editor, change the words between the tags — for example, turning `<h1>Skin that speaks for itself.</h1>` into whatever you'd rather say — and save. Preview it using the steps above. When you're happy, save the change to the project and the live site will catch up within a minute or two.

---

*Glow is a fictional studio, created as a design and development sample.*
