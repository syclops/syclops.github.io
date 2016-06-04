---
layout: post
title: "Better flashcards with Clank"
date:   2016-06-03 23:19:00 +0200
categories: project idea
---
*Disclaimer: I'm not familiar with the inner workings of Anki, so this feature
may already exist, and some of the things I claim about Anki may be wrong.*

I'm a longtime user of [Anki](http://ankisrs.net/) for learning languages.
Besides its spaced-reptition learning system, one nice feature of Anki
flashcards is called [Cloze deletion](https://en.wikipedia.org/wiki/Cloze_test),
where you can specify a blank to be filled in with an optional hint, like so:

*In fourteen-hundred ninety-two<br/>[person] sailed the ocean blue*

This card can then be revealed to show the answer:

*In fourteen-hundred ninety-two<br/>**Columbus** sailed the ocean blue*

Anki is pretty cool in that you can specify multiple blanks in a single
question, along with answers that should be hidden simultaneously. For example,
you can specify a Cloze deletion for *fourteen-hundred ninety-two* and get

*In [year]<br/>[person] sailed the ocean blue*

I've tried using Anki for a variety of subjects, but I've personally found that
it's most helpful for languages. I've been learning German for the past two and
a half years, and I can create cards like

*[das] [Kind] - the [child]*

where each item in square brackets indicates a separate Cloze deletion. In this
way, I can have a single card to test (1) the gender of the noun in German, (2)
the German word, and (3) the English translation.

Similarly, I can use Cloze deletions to test my skills in translating phrases
over full sentences, like so:

*Er hat gesagt, [that he had already eaten].*

My problem when using these types of cards is that over time, I get used to the
*card* rather than to the *concept*. In other words, I tend to see the beginning
of the sentence in German and associate it with the partial phrase, rather than
internalizing the actual translated part of the sentence.

To overcome this problem, I came up with an approach that I call *conceptual
templates*. The idea is to create a template like this:

*[phrase] [article] [adjective] [noun]*

where *[phrase]* is one of *{(empty), für, mit}*. Then, I can create tagged
flashcards like this:

*[das:article] [Kind:noun] - the [child:noun_en]*

*[rot:adjective] - [red:adj_en]*

This allows me to classify parts of a flashcard as matching parts of a template.
Then, in addition to reviewing individual flashcards as normal, I can also do
*templated reviews*, where I'll be asked to fill in a randomly-generated
flashcard like this:

*mit [the] roten Apfel*

Then, this card would be linked to the *concept* that *mit* is followed by a
dative article, and rather than scheduling my next review for the correct word
*dem*, the software would schedule the next review for the idea that *mit* is
associated with the dative case (or more specifically, a dative definite
article in this case, no pun intended).

Using this system, reviewing flashcards can allow me to build my skills in
grammatical concepts and vocabulary simultaneously, while preventing me from
getting used to a single card. There's of course the chance that a generated
card may be very strange, but that can also help with memorability.

I thought about creating a system called Clank (Command-Line ANKi) to implement
this system on a simple command-line interface. There are a lot of pieces,
though, including database management, the review scheduling algorithm,
interface design, etc. Hopefully I can chip away at each of these pieces one
week at a time, but if you read this and have any interest in helping out, I'd
love to hear from you.
