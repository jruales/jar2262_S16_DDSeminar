# Spanish Etymology Scraper

Scrapes the *Real Academia Española* (RAE, tranlation: "Royal Spanish Academy") Spanish dictionary for etymology for top N most occurring words in the *Corpus de Referencia del Español Actual* (CREA, translation: "Reference Corpus of Current Spanish") Spanish corpus, for N = 1000, 5000, and 10000. The full RAE Spanish dictionary currently contains more than 93000 entries. Not all words that appear in the CREA corpus are guaranteed to be in the Spanish dictionary.

* More information about the CREA Corpus: http://www.rae.es/recursos/banco-de-datos/crea
* More information about the RAE Spanish dictionary: http://www.rae.es/diccionario-de-la-lengua-espanola
* Abbreviations employed by the RAE Spanish dictionary: http://www.rae.es/sites/default/files/Abreviaturas_y_signos_empleados.pdf

|File or directory      | Description                                                          |
|-----------------------|----------------------------------------------------------------------|
|`./unigram_counts/`    | CREA corpus unigram count files                                      |
|`./main.ipynb`         | The main program in a Jupyter notebook                               |
