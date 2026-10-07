# Akkadian Translator Workbench 
> & Interlinear/Lexicon Builder

This repo is mostly informational details for an interlinear development tool I created decades ago and have recently migrated to the latest web technology. I created the tool as a means to learn Koine Greek when I was taking courses for my master's. 
However, I designed it to be language-agnostic. To test multiple languages, I created a language pack for Akkadian (Old Babylonian), and I am really impressed with how well it works. Of course, I am not an Akkadian scholar. But working through this
piqued my curiosity in Akkadian again, something I have not really worked on in a decade or more. So, I am working through the grammar texts again, and I really enjoy it. So, my intent is to keep working on the tool as well and continue making it better. 

### Why hasn't this been done before?
I do understand that there are issues and no one has created something like this for Akkadian for valid reasons. But even so, I think I can work around much of that and make the app useful for students trying to learn, even if it is not useful for scholars. 
I am open to suggestions and I would really like some thoughts as to the issues with this from a scholarly perspective. Meaning... what is it that I don't know? Why can't we build an interlinear for Akkadian?  

### Screenshots of the Application
Below are some screenshots from the app itself. I am working to get that published in a way where I can make it available for free online. It has some core features I built for a commercial product for learning Koine Greek, so I don't want to open source that 
part of the code unless I decide to abandon the commercial side. But I can host it online for free with the Akkadian language pack. That is what I am working to do. 

### Other Documents stored here
This repo stores several Akkadian (Old Babylonian) documents used in an interlinear building tool. I will eventually publish the tool 
here, but I need to figure out what sort of version I want to share as an open-source project. The core of the app was built as a commercial 
product to help students learn Koine Greek, and I don't want to open-source the whole thing. Until I make that call and publish an open-source
version, I am sharing some of the texts, grammar setup, etc. here for others to see and use in discussions. 

## Codex Hammurab(p)i

This is the reader view displaying the transliteration and cuneiform signs in a column display that aligns to the original. Everything else is turned off. Note that AN is selected and its lexicon entry is displayed on the right.  
If you need some help, you can set a gloss threshold. So, maybe any word that shows up less than 10 times in the text, you have the reader gloss it for you. Typical of the 
printed readers that show the translation of words based on a set threshold. But here you can set it as you wish.

<img width="949" height="673" alt="image" src="https://github.com/user-attachments/assets/41a18560-e002-41ce-a3c9-2b8229c9dac5" />

This is the same view, but I have turned on the lemma, parse tag, and gloss. The details here come from Harper's 1904 translation. 

<img width="472" height="471" alt="image" src="https://github.com/user-attachments/assets/d693b11f-83d1-4720-83a1-0ad8e6172d9c" />

This view is the same, but I have turned on full category names for the parsing tag to help students new to the shorthand. 
(Click on the image to zoom in)

<img width="530" height="633" alt="image" src="https://github.com/user-attachments/assets/5ec5ea0e-cb9b-4329-aadc-e1d80314b810" />

Here's the clause-style display, creating lines of text based on the clause. I am trying to come up with different ways to display the text better.

<img width="1507" height="490" alt="image" src="https://github.com/user-attachments/assets/40e51485-5649-4096-8e0b-4717408b86b4" />

## Gilgamesh

Here's the _Epic of Gilgamesh_ text. I have set _ana_ in the lexicon and told it to auto-gloss it any time it finds it. So once I set this up, it will display the lemma, parse tag, 
and lexicon entry for me. The idea here is that I can work through and set up my lexicon and apply it to the whole text or other texts as I see fit. But when it comes time to 
translate the text, I can use the gloss as a helper, but it is up to the translator to decide the translation... not the lexicon.   

<img width="753" height="622" alt="image" src="https://github.com/user-attachments/assets/9e3826c8-127e-4570-ae70-ca705199faa2" />

### Translation Mode

In the translation mode, I can set up my lexicon entries as I work through the text. Or I can go to the lexicon page and set up entries there. Here on the translation page
can enter the translation and save it for only this text, mark the word as untranslated, or I can tell it to create this as a new lexicon entry and auto-gloss this word if
it shows up again.

<img width="962" height="652" alt="image" src="https://github.com/user-attachments/assets/d312f550-c618-4cb5-b5e1-2281d2d7f9a0" />

### Word Order

Once you work through your translations, you will need to set the word order. When translating from Akkadian to English, you will need to add filler words, punctuation, and mark 
words that do not translate. To do this, I have a page to manage these. The idea here is that you set it up once and the application saves it as a sort of algorithm. You then 
apply that to the text to generate your final translation. This way, as you go back to your translations and adjust them, you just regenerate the text and your word order, 
punctuation, added words, excluded words, etc. are all automatically applied. 

I added punctuation, the, and of the to the text. But I did not modify the word order. But I could have just dragged and drop any of the words in any order and the app would maintain that.

<img width="745" height="339" alt="image" src="https://github.com/user-attachments/assets/19ddfee3-a6c4-4b89-beef-d1d8f013ab30" />

In my final translation, the word order, punction, excluded or added words, etc are all included. I have the line numbers listed as well, but you will be able to exclude those if you wish.  

From here, you can save it as a text file, export it to Word, or export it as a file that you can send to someone else to load into their copy of the app. So a teacher could create
the files and send it to all of their students to load into the app and work with. Or someone learning could export it to Word. But it is already saved in the app itself and you can
back that up to your local computer if you'd like. 

<img width="795" height="359" alt="image" src="https://github.com/user-attachments/assets/6b224260-eea8-43e3-b169-7f8282e2ac85" />

### Sentence Diagrammer & Outline Generation

Helps you to see and align the structures in the clauses to see relationships and parts of speech. This is set up for Koine Greek currently, but it works well enough to show you the idea. I need to add the Akkadian grammar and parse rules to make this work correctly.

# Many more features...
* Reader
  * Show signs only
  * Show transliterations only (with or without lemma)  
* Sentence Diagrammer & Outline Generator
  * Using an algorithm over the parse-tags to create a sentence diagram. 
* Parsing practice pages/sheets
  * Practice your parsing and the app will tell you when you get it wrong.
  * Practice your translation and the app will grade you. It uses a distance equation against the lexicon to grade your translation.   
* Lexicon Builder
  * Build your own custom lexicon(s)
    * Create a lexicon for a given text. Say every word in Codex Hammurabi or Gilgamesh
    * Create your own and choose which works to include from translations or existing lexicons already supported.
    * Manage your lexicon as you see fit.
    * Export it to Word or share it with others.   
* Interlinear Builder
  * Choose which features you want to display
  * Export to Word
  * Share it with others
* Test & Quizzes
  * Turn any line or clause of text into a test or quiz and track your progress.
  * Turn any line or clause into a flashcard drill... "know it, don't know it" style.
  * I will be adding new features here to create text questions and other features I think would be helpful.
* Import/Export 
  * Import transliteration and have it create the cuneiform and auto-gloss anything that is already in your lexicon(s).
  * Create your own transliteration from scratch to create your own texts, translations, quizzes, tests, documents, etc.
  * Export any of the documents to share with others or export to Word.
* Supports other languages.
  * Koine Greek was what I started with and is already supported.
  * New language packs can be added.
