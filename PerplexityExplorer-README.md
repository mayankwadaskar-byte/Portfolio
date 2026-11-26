# Perplexity Explorer

An interactive lab that shows how surprised a real language model is by your sentence. It runs DistilGPT-2 in the browser and explains perplexity step by step.

## Problem

Perplexity is the standard way to evaluate language models, but the single number is hard to understand. This page shows where it comes from, token by token.

## What it does

| Section | What it does |
|---|---|
| Analyze | Scores every token of your sentence. Shows a heatmap, a surprise-per-token chart in bits, and the step-by-step maths. Copy a summary or download CSV. |
| Predict | Shows the model's top guesses for the next token. Click one to add it, or auto-write 10 tokens. |
| Compare | Runs two sentences head to head (for example, the same words in a different order). |
| By hand | Set token probabilities with sliders and watch perplexity update live. No model needed. |
| Scoreboard | Ranks every analysed sentence from most natural to most surprising. |
| Learn | A short explanation of perplexity and three equivalent formulas. |

## How it works

`PPL = exp(−1/N · Σ ln P(token_i | previous tokens))`

The model reads left to right. For each token it gives the probability it expected that token, given everything before it. Perplexity is 2 raised to the average surprise in bits: the model's effective number of equally likely choices per token.

## Tech stack

JavaScript, HTML and CSS, [Transformers.js](https://github.com/xenova/transformers.js) 2.17 and the DistilGPT-2 model from Hugging Face. The model (about 80 MB) downloads once and is cached by the browser.

## Run it

Open `index.html` in a browser with an internet connection for the first model download.

## Author

Mayank Wadaskar ([@mayankwadaskar-byte](https://github.com/mayankwadaskar-byte)), B.Tech CS (AI/ML), Newton School of Technology. Solo project, built for a class assignment.
