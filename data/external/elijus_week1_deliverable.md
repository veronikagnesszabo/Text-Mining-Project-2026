# Elijus — Week 1 Deliverable
**Due: 20th April | Text Mining Project 2026**

## 2. Similar Project Research

Below are three comparable text mining / sentiment analysis projects that can serve as inspiration for methodology, structure, and presentation.

---

### Project 1 — Twitter Sentiment Classification (sharmaroshan, GitHub)
**Link:** https://github.com/sharmaroshan/Twitter-Sentiment-Analysis

This is a complete NLP pipeline for classifying tweet sentiment (positive/negative) using classical ML models. Covers the full workflow: raw text → cleaning → TF-IDF vectorisation → Naïve Bayes / Logistic Regression → evaluation.

It's relevant because it:
- Provides a clean, well-documented end-to-end pipeline we can use as a structural template for our own notebooks.
- Demonstrates how to handle noisy, informal text — useful reference even though TED transcripts are more formal.
- Shows how to set up train/test splits and evaluation metrics (F1, accuracy) which we will need for validating our sentiment tool choices.

**Key Takeaway:** The preprocessing module is reusable. Their tokenisation, stopword removal, and lemmatisation steps are a solid starting point for our `src/preprocessing.py`.

---

### Project 2 — Emotion Detection from Text (Frontiers in Psychology, 2023)
**Link:** https://www.frontiersin.org/journals/psychology/articles/10.3389/fpsyg.2023.1190326/full

This is a peer-reviewed study that applies machine learning classifiers (SVM, Naïve Bayes, decision trees) to detect discrete emotions in text. It discusses the distinction between sentiment polarity (positive/negative/neutral) and emotion recognition (joy, anger, sadness, fear, surprise) — exactly the split our project needs to navigate across RQ1 and RQ3.

It's relevant because it:
- Directly addresses the methodological question our project faces: when to use sentiment analysis vs. emotion detection, and how to combine both.
- Reviews lexicon-based methods (NRC, LIWC) alongside ML classifiers, helping us justify our tool choices (VADER for polarity, NRC for discrete emotions).
- Discusses how emotion labels map to audience response — relevant to linking emotional content with YouTube engagement in RQ2.

**Key Takeaway:** The paper's framework for separating *valence* (positive/negative) from *emotion category* (the 5-emotion model) is directly applicable to our analysis design. Maybe worth citing in Veronika's methodology section too?
