# One Sign, Many Shapes

*Why a cuneiform reader shows standardized letterforms, and why Greek and Hebrew readers have been doing the same thing for five hundred years.*

## The problem in one sentence

The Code of Hammurabi was carved around 1754 BCE in Old Babylonian monumental script; the cuneiform you see on a screen is drawn in Neo-Assyrian forms about a thousand years younger, because that is what the available fonts contain. The *signs* are right. The *shapes* are from the wrong millennium.

This looks at first like a defect to be fixed. It is better understood as the same compromise every printed edition of an ancient text has already made — and one that Greek and Hebrew made so long ago that nobody notices any more.

## Cuneiform never had one shape

Cuneiform was written for roughly three thousand years, from the proto-cuneiform tablets of Uruk (c. 3200 BCE) to the last datable astronomical texts of the first century CE. Over that span the script changed continuously:

- **Proto-cuneiform and Early Dynastic** (c. 3200–2350 BCE): still visibly pictographic, drawn with a pointed stylus, originally in vertical columns read top to bottom.
- **Old Akkadian and Ur III** (c. 2350–2000 BCE): fully wedge-based, rotated to horizontal reading, the pictures no longer legible as pictures.
- **Old Babylonian** (c. 2000–1600 BCE): the period of our text. Fewer wedges per sign than earlier, and a sharp split between the everyday cursive of letters and contracts and the formal lapidary hand of monuments.
- **Middle and Neo-Assyrian / Neo-Babylonian** (c. 1500–500 BCE): further simplification, with the Neo-Assyrian forms of the great Nineveh libraries becoming, by accident of what survived and what was published first, the "textbook" shapes.

So "Old Babylonian script" is not one thing either. The Hammurabi stele is written in a deliberately **archaizing monumental hand** — formal, closer to older ceremonial writing than to the cursive a scribe of Hammurabi's own chancery used for a letter that same week. A perfectly period-accurate font for the stele would still be wrong for the letters of the same king.

That is the first thing worth saying plainly: there is no single correct shape to standardize *to*. There is a continuum, and any choice is a choice.

## Unicode encodes signs, not shapes

The Unicode Cuneiform block (U+12000–U+123FF, added in Unicode 5.0 in 2006, with numerals and punctuation following at U+12400) encodes **sign identity**, not letterform. The character U+12038 is the sign AŠ. It is not "AŠ as carved on the Hammurabi stele" or "AŠ as impressed at Nineveh"; those are two renderings of one character, and supplying them is the font's job.

This is the same model that lets the same English sentence be set in blackletter, a Renaissance roman, or a modern grotesque without becoming different text. It is also what makes everything else possible: search, sorting, concordancing, transliteration, copy and paste. If every period's form of AŠ were its own codepoint, the "same" sign would be a dozen unrelated characters and no search would ever match across them.

Unicode did draw a line, but not where one might expect. **Early Dynastic Cuneiform** got its own block (U+12480–U+1254F, Unicode 8.0, 2015) because those forms were judged too distant to unify. Old Babylonian and Neo-Assyrian were *not* separated — they were judged to be the same signs differently drawn. That is an editorial judgement, and it is the judgement that produces the mismatch described here.

The practical consequence: **period-accurate letterforms are a font problem, not an encoding problem.** Nothing about the data has to change to fix it. Someone has to draw the font.

## Greek: the printed page is a thousand years younger than the text

Open any critical edition of the Greek New Testament. What you see is:

- **Lowercase letters.** The New Testament was written in majuscule (capitals). Greek minuscule is a ninth-century CE development — some eight hundred years later.
- **Word spaces and punctuation.** The manuscripts are *scriptio continua*, an unbroken run of letters. Spacing is an editorial addition.
- **Accents and breathings.** Devised in the Hellenistic period (traditionally credited to Aristophanes of Byzantium, c. 200 BCE) as an aid for non-native readers, but not written consistently until the Byzantine period.
- **Letterforms from Renaissance Italy.** The first printed Greek types, cut for Aldus Manutius in Venice from the 1490s, imitated the cursive Byzantine hand of contemporary scribes, ligatures and abbreviations included — hundreds of separate sorts. The eighteenth and nineteenth centuries simplified that drastically; the Porson type, based on Richard Porson's handwriting and cut for Cambridge in the early nineteenth century, became the standard for British classical printing, and most modern Greek faces descend from that tradition.

A student reading SBLGNT in a modern digital face is therefore looking at a script no first-century writer used, with diacritics applied by a convention centuries later, in letterforms designed between the Renaissance and the Victorians. This is not controversial. It is simply what a *reading edition* is.

## Hebrew: an entirely different script, plus invented vowels

Hebrew makes the point even more sharply, because what changed was not the letterforms but the **script itself**.

The earliest biblical Hebrew was written in Paleo-Hebrew, a direct descendant of the Phoenician alphabet. After the exile the square "Assyrian" script (*ktav Ashuri*), borrowed from Imperial Aramaic, displaced it, and that is the script of every printed Hebrew Bible. The tradition was aware of the switch and discussed it openly — the Talmud (Sanhedrin 21b–22a) records the view that the Torah was given in one script and the people changed to the other in Ezra's time. The Dead Sea Scrolls show both in use side by side, with some scribes writing the divine name in the old script inside a text otherwise in the new.

On top of that:

- **Vowel points and cantillation marks are Masoretic**, developed by the Tiberian school roughly between the seventh and tenth centuries CE — well over a thousand years after the consonantal text they annotate. The Aleppo Codex (c. 930) and the Leningrad Codex (1008/1009), the base of modern critical editions, are the standard witnesses.
- **The printed letterforms are Renaissance Italian.** Hebrew typography takes its shapes from Sephardi and Ashkenazi manuscript hands by way of fifteenth- and sixteenth-century printers; Daniel Bomberg's Rabbinic Bibles (1516–17, and the 1524–25 edition prepared by Jacob ben Hayyim) fixed a page layout still recognizable today.

So a seminary student reading BHS is reading a script the original authors did not use, with vowels added a millennium and a half later, in types cut in Venice. Nobody considers this a scandal, because everybody understands the division of labour: the edition is for *reading the language*; the manuscript is for *studying the object*.

## What Assyriology already does

The field has had a settled answer to this for a century, and it is not "pick one period and pretend".

The standard reference sign lists — Labat's *Manuel d'épigraphie akkadienne* and Borger's *Mesopotamisches Zeichenlexikon* (the source of the MZL numbers used in this project) — are laid out as a table: **one row per sign, one column per period.** A single sign's identity runs across the row, and its Old Akkadian, Old Babylonian, Middle Assyrian and Neo-Assyrian forms sit beside each other so you can see the shape change.

That structure encodes exactly the distinction at issue here: the *sign* is stable and is what you learn; the *form* is variable and is what you learn to recognize later, when you work with a particular object. Reading cuneiform and reading a particular hand are two different skills, and palaeography is the second one.

## What this means for a reading app

A reading tool should teach the first skill well and be honest about not teaching the second.

Concretely, that means:

1. **Store sign identity, not pictures.** Signs are stored as Unicode characters and drawn by a font — no images anywhere. Text stays searchable, selectable, copyable, and scalable, and the sign list can match a pasted glyph by simple string comparison.
2. **Name the mismatch rather than hiding it.** A student who learns the shapes from this app and then opens a photograph of the Louvre stele should have been told in advance that the shapes will not match, and why.
3. **Treat a period face as an enhancement, not a correction.** Because identity and shape are separate, an Old Babylonian font could be swapped in later and no stored data would change — not one word id, not one reading, not one parse.
4. **Point at the facsimile.** For the object itself, the photograph and the hand copy are the authorities, not the screen.

### Where this project currently stands

The Akkadian texts here are drawn with **Noto Sans Cuneiform**, loaded from Google Fonts under the SIL Open Font License. Its forms are Neo-Assyrian. Sign values and sign names come from the **Oracc Sign List**, which releases its data into the public domain under CC0, and MZL numbers come through it from Borger.

An Old Babylonian face remains an open question. Two candidates are known and neither is settled:

- **Santakku / SantakkuM** — Old Babylonian forms, but licensed for non-commercial use only, which rules it out for anything that might become a paid or publicly hosted product.
- **CuneiformOB** — reported to derive from the OFL-licensed CuneiformComposite, but its own licence terms need to be confirmed from the font's own distribution before it is bundled anywhere.

Until one of those is resolved, the honest position is the one above: right signs, standardized shapes, clearly labelled.

## A note on the sources

Dates here are approximate and conventional; Assyriological chronology in particular has competing schemes (the Hammurabi date given follows the Middle Chronology, and High and Low chronologies shift it by decades to a century). Before citing any of this in published work, check:

- the Unicode Standard's own cuneiform block descriptions for the unification rationale;
- Labat or Borger directly for the period-column layout and specific sign forms;
- a palaeography of the Hammurabi stele specifically, for the claim that its hand is archaizing rather than ordinary Old Babylonian cursive;
- the font licences named above, from the fonts' own distributions rather than secondary summaries.

The general argument — that every reading edition of an ancient text standardizes its script, and that this is a feature of editions rather than a failure of them — is uncontroversial. The particulars are where the care is needed.
