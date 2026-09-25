# Financial News Sentiment Classification

> **Status: work in progress.** This README is updated as each step is completed.

Classifying sentences from financial news as **positive**, **neutral** or **negative**, and comparing a classical NLP baseline with a fine-tuned transformer.

## Why this project

Thousands of financial news items are published every day, far more than any analyst can read. Automatically detecting whether a piece of news is good or bad for a company is a building block for news monitoring and trading signals.

The project also answers a simple question: **how much does a transformer actually gain over a word-counting baseline, and where?** Word-based models struggle with context, for example *"The company's loss decreased"* is good news despite the word *loss*.

## Dataset

**Financial PhraseBank** (Malo et al., 2014): about 4,800 English sentences from financial news, each labelled by finance experts. The classes are imbalanced (neutral is the majority class).

## Approach

1. **Baseline**: TF-IDF features + logistic regression (scikit-learn)
2. **Transformer**: fine-tuning FinBERT with Hugging Face Transformers (PyTorch)
3. **Error analysis**: where each model fails (negations, context, ambiguous sentences)
4. **Deployment**: FastAPI endpoint packaged with Docker, public demo on Hugging Face Spaces

## Evaluation

Main metric: **macro-F1**. Because the classes are imbalanced, accuracy is misleading: a model that always predicts "neutral" would look decent on accuracy but score poorly on macro-F1, which averages the F1-score of each class equally.

## Roadmap

- [ ] Data loading and exploration
- [ ] TF-IDF + logistic regression baseline
- [ ] Fine-tuned transformer (FinBERT)
- [ ] Model comparison and error analysis
- [ ] FastAPI + Docker
- [ ] Hugging Face Spaces demo

## Results

Coming soon.

## Tech stack

Python, scikit-learn, PyTorch, Hugging Face Transformers, FastAPI, Docker
