# Project: Analysis of Etymology of Spanish Words

## The Problem

As a native Spanish speaker, I learned as a child to consider as commonplace some words that to an English speaker seem overly formal, specific, or obscure. Words such as *utilizar* (English equivalent: "to utilize"), *cotidiana* ("quotidian"), *inundar* ("to inundate"), and *mayúscula* ("majuscule") are assumed to be understood by most people. In terms of common words, it might be that Spanish has a stronger influence from Latin than English does, but it would be nice to quantify this statement and try to understand the structure that this Latin influence brings to Spanish words.

Aside from Latin, Spanish has influence from, among others, Greek, Arabic, native American languages such as Kichwa and Nahuatl.

I would like to understand the structure behind the modern Spanish language's vocabulary and how other languages (and even old Spanish) have influenced it. I would like to find out if languages can be seen as evolving in a generative process, where new words that are created follow a certain uniformity and structure conditioned on its origins (regardless of whether it comes from the same or another language, including an older version of the same language).

To understand the etymology of Spanish, there are several options in terms of models that could be built. Three examples include:

* A generative model that constructs new spanish words given a categorical distribution of influences, like a mixture model with a mixture of origins or influences.
* A classifier that predicts the etymological origin of a previously unseen word.
* Embedding words into a low-dimensional latent space that captures the influence of other languages and finding patterns in the visualization of such latent space.

## The Data

### Etymology Lookup
* The *Real Academia Española* (RAE, English:"Royal Spanish Academy") has one of the most prestigious Spanish dictionaries available online at http://dle.rae.es/ . This dictionary contains the etymology for many (not all) of its entries and should be relatively simple to scrape for data.
* Wikipedia's lists of Spanish etymology: https://en.wikipedia.org/wiki/Influences_on_the_Spanish_language#Lists_of_Spanish_etymology
* https://es.wikipedia.org/wiki/Anexo:Quechuismos_en_el_idioma_espa%C3%B1ol
* https://es.wikipedia.org/wiki/Anexo:Nahuatlismos_en_el_idioma_espa%C3%B1ol
* https://es.wikipedia.org/wiki/Americanismo_(ling%C3%BC%C3%ADstica)
* https://en.wikipedia.org/wiki/Latin_influence_in_English

### N-Gram Counts
* The CREA Spanish corpus page has a list of unigram frequency counts sorted by frequency: http://corpus.rae.es/creanet.html (More info about the corpus: http://www.rae.es/recursos/banco-de-datos/crea)
* Google N-grams has them in Spanish, English, and other languages: http://storage.googleapis.com/books/ngrams/books/datasetsv2.html

### Misc.
* "Awesome Linguistics Resources for Spanish" https://github.com/dav009/awesome-spanish-nlp
