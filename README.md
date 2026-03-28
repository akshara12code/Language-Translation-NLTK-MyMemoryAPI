# Language-Translation-NLTK-MyMemoryAPI
# NLP Language Translator

A command-line language translator built with NLTK that runs a full NLP pipeline on every input before translating using the MyMemory API.

## What It Does

For every piece of text you enter, the program runs through 7 NLP steps and prints a detailed report:

1. **Language Detection** — auto-detects the input language using character n-grams
2. **Text Normalization** — strips extra whitespace and cleans up the input
3. **Tokenization** — splits text into sentences and individual word tokens
4. **Stopword Removal** — filters out common filler words (e.g. "the", "is", "a")
5. **POS Tagging** — labels each word as noun, verb, adjective, etc.
6. **Named Entity Recognition** — identifies people, places, and organizations
7. **Translation** — sends the cleaned text to the MyMemory API and returns the result

## Supported Languages

20 languages including English, Hindi, French, German, Spanish, Italian, Portuguese, Russian, Chinese, Japanese, Korean, Arabic, Turkish, Bengali, Marathi, Tamil, Urdu, Dutch, Polish, and Greek.

## Installation

```bash
pip install nltk requests langdetect
```

NLTK data packages are downloaded automatically on the first run.

## Usage

```bash
python main.py
```

1. Select a **source** language by number
2. Select a **target** language by number



<img width="628" height="473" alt="Screenshot 2026-03-25 002331" src="https://github.com/user-attachments/assets/33f70c5c-a5ae-411c-860e-1a1d61a5e0db" />
<img width="632" height="694" alt="Screenshot 2026-03-25 002423" src="https://github.com/user-attachments/assets/0e7d8ea3-c119-4f6f-b232-cc9486d30477" />

3. Type any text (up to 500 characters) to translate
<img width="648" height="735" alt="Screenshot 2026-03-25 002440" src="https://github.com/user-attachments/assets/ef566606-5b55-45f6-a807-8eb84384bc29" />
<img width="617" height="355" alt="Screenshot 2026-03-25 002457" src="https://github.com/user-attachments/assets/3643fb52-52a9-4e85-bc0c-b39d30140ae3" />


## Example

```
Enter text: The Eiffel Tower is located in Paris.

─────────────────────────────────────────────────────
  NLP PIPELINE REPORT
─────────────────────────────────────────────────────

[1] Language Detection
    Detected  : English (en)

[2] Text Normalization
    Normalized: The Eiffel Tower is located in Paris.

[3] Tokenization
    Word count: 8

[4] Stopword Removal
    Removed   : ['The', 'is', 'in']

[5] Part-of-Speech Tagging
    Eiffel    → Proper Noun (NNP)
    Tower     → Proper Noun (NNP)
    located   → Verb (past participle)
    Paris     → Proper Noun (NNP)

[6] Named Entity Recognition
    'Eiffel Tower' → ORGANIZATION
    'Paris'        → GPE

[7] Translation  (English → French)
    Result: La Tour Eiffel est située à Paris.
```

## Notes

- Translation is powered by the free [MyMemory API](https://mymemory.translated.net/) and requires an internet connection.
- NLP features (POS tagging, stopword removal, NER) work best on English and other Latin-script languages.
- Input is limited to 500 characters per request.
