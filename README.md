# Epitran

A library and tool for transcribing orthographic text as IPA (International Phonetic Alphabet).

## Usage

The principle script for transliterating orthographic text as IPA is `epitranscriber.py`. It takes one argument, the ISO 639-3 code for the language of the orthographic text, takes orthographic text at standard in and writes Unicode IPA to standard out.

```
$ echo "Düğün olur bayram gelir" | epitranscribe.py "tur"
dyɰyn oluɾ bajɾam ɟeliɾ
$ epitranscriber.py "tur" < orthography.txt > phonetic.txt
```

Additionally, the small Python module ```epitran``` can be used to easily write more sophisticated Python programs for deploying the **epitran** mapping tables. This is documented below.

## Using the `epitran` Module

The functionality in the `epitran` module is encapsulated in the very simple `Epitran` class. Its constructor takes one argument, `code`, the ISO 639-3 code of the language to be transliterated.

```
>>> import epitran
>>> epi = epitran.Epitran('tur')
```

The `Epitran` class has only one "public" method (to the extent that such a concept exists in Python): the `transliterate` method:

**transliterate**(text):
Convert `text` (in orthography of the language specified in the constructor) to IPA, which is returned.

## Piplines