# Preprocessing

## Overview

The preprocessing pipeline was built using spaCy (`en_core_web_sm`) and NLTK. It was applied to the transcript column of the dataset. The pipeline consists of three steps: tokenisation, stopword removal, and lemmatisation.

## Data

The main dataset (`ted_main.csv`) contains 2550 TED talks. A separate `transcripts.csv` file containing the full transcript and url for each talk was merged with the main dataset using the `url` column as the key. After merging, 2467 talks were retained.

## Pipeline

The following function was applied to each transcript:

```python
def preprocess(text):
    doc = nlp(str(text))
    tokens = [token.lemma_.lower() for token in doc
              if not token.is_stop and not token.is_punct and not token.is_space]
    return tokens
```

- **Tokenisation**: spaCy splits the text into individual tokens.
- **Stopword removal**: common words such as "the", "a", and "is" are removed.
- **Lemmatisation**: each token is reduced to its base form (e.g. "running" → "run").

Two output columns were produced:
- `clean_tokens`: a list of preprocessed tokens.
- `clean_text_joined`: the tokens rejoined into a single string, ready for sentiment analysis.

## Output

The final preprocessed dataset is saved as `results/preprocessed_full.csv`.
