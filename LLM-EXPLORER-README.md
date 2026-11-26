# LLM Pipeline Explorer

An interactive, single-file explainer of the first steps of a large language model: tokenization, embeddings and similarity. It runs entirely in the browser, with no libraries and no backend.

## Problem

Tokenization, embeddings and similarity are hard to picture from formulas alone. This page lets you change the inputs and watch each step happen.

## What it does

| Step | What you see |
|---|---|
| Tokenizer | Build a vocabulary from a training corpus. Drag the slider to shrink it and watch rare words split into subwords. Each token gets an integer ID. |
| Embeddings in 3D | Each sentence becomes a 36-number vector. PCA projects it to 3D. Rotate, zoom, and click a point to see its nearest neighbours. K-means groups the points into clusters. |
| Similarity matrix | A heatmap of cosine similarity between every pair of sentences, measured in the original 36 dimensions. |

## How it works

- **Subword tokenizer:** greedy longest-match, WordPiece-style.
- **Sentence vectors:** a small hand-written topic lexicon plus hashed character trigrams.
- **PCA:** power iteration with deflation, reducing 36 dimensions to 3.
- **Clustering:** k-means.
- **Rendering:** a custom perspective camera drawn on a 2D canvas.

## Simplified on purpose

- The embeddings are not from a trained neural network.
- Subword pieces come from the vocabulary, not from learned merges as in BPE.
- Words outside the lexicon land in fairly arbitrary positions.

## Tech stack

Vanilla JavaScript, HTML and CSS, Canvas 2D. One file, zero dependencies, light and dark themes.

## Run it

Open `index.html` in a browser. Nothing to install.

## Author

Mayank Wadaskar ([@mayankwadaskar-byte](https://github.com/mayankwadaskar-byte)), B.Tech CS (AI/ML), Newton School of Technology. Solo project.
