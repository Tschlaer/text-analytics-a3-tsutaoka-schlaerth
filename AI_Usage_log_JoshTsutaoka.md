# AI Usage Log — Student A
## BSAN 6200: Text Mining & Social Media Analytics
## Assignment 3: Topic Modeling

---

## Overview

This log documents all AI assistance used during the implementation of Assignment 3.
Per Tier 3 guidelines, AI was used strictly for code implementation and debugging.
All topic interpretation, topic naming, and business insights were completed
independently without AI assistance.

---

## AI Tool Used
- Claude (Anthropic) — claude.ai chat interface

---

## AI-Assisted Tasks (Permitted)

### Data Loading & Environment Setup
- Debugged `kagglehub.load_dataset()` ValueError caused by unsupported file extension in the dataset — the adapter requires a top-level file but the dataset uses a nested folder structure (movie folder → metadata.json + movieReviews.csv)
- Generated directory-walking loader using `os.listdir()` to iterate through each movie folder and load `movieReviews.csv` and `metadata.json` separately
- Identified that ~2,197 Dark Knight rows were unrecoverable due to source-level CSV corruption; generated multi-encoding fallback loader using `on_bad_lines='skip'` with utf-8, latin-1, and cp1252 attempts
- Generated data limitations markdown cell documenting missing rows
- Assisted with pip install commands for gensim, wordcloud, and spaCy English model
- Resolved `ModuleNotFoundError: No module named 'gensim'` — identified that a runtime restart was required after pip install before the import would work

### Step 1 — Group Definition
- Generated group assignment lambda mapping 10 movies into 3 thematic groups: Group1_Superhero, Group2_CrimeDrama, Group3_ActionOther
- Generated per-group and per-movie review count verification print

### Step 2 — EDA
- Generated review length calculation and per-group descriptive statistics
- Generated length distribution histogram (1×3 subplot, colored by group, red dashed median line)
- Generated user rating distribution and vocabulary size calculations
- Generated horizontal bar charts showing top 20 raw tokens per group (replacing word clouds at student request)

### Step 3 — Text Preprocessing
- Generated spaCy load with parser and NER disabled for speed
- Generated domain-specific custom stopword set covering generic review filler, sentiment words, movie title words, and review meta-language
- Generated `preprocess()` function: lowercase, HTML strip, regex cleaning, spaCy lemmatization, stopword filtering, min length > 2, alpha-only filter
- Generated apply cell with before/after example, short review filter (< 5 tokens), and save to `data/processed/imdb_reviews_clean.csv`
- Generated cleaned token bar charts (post-cleaning, same format as raw charts)
- Added extended stopwords (`end`, `guy`, `man`, `world`, etc.) after reviewing initial topic outputs that showed noise terms diluting topic quality

### Step 4 — Feature Engineering
- Generated CountVectorizer setup with separate vectorizers per group (`max_df=0.90`, `min_df=10` later updated to `min_df=15`, `max_features=5000`, `ngram_range=(1,2)`)
- Generated DTM shape verification and top 20 token frequency output per group

### Step 5 — Topic Modeling
- Generated `display_topics()` and `get_coherence_score()` helper functions
- Generated k tuning sweep across k ∈ {5, 8, 10, 12, 15} for all 3 groups with coherence and perplexity tracked per iteration
- Generated coherence vs k line plot with red dashed line marking k=10
- Generated final LDA fitting loop at k=10 across all 3 groups (`max_iter=20` later updated to `max_iter=50` to improve coherence scores)
- Generated model summary table (group, k, coherence, perplexity)
- Generated 2×5 topic word weight bar charts per group colored by group identity
- Generated coherence before vs after preprocessing comparison cell
- Generated final evaluation summary table and grouped bar chart showing coherence and perplexity before vs after preprocessing for all 3 groups
- Explained why k=10 was kept despite tuning sweep showing k=5 or k=8 as optimal — assignment requirement with documented tradeoff in methods section

**Student A:** Josh Tsutaoka
**Course:** BSAN 6200 — Text Mining & Social Media Analytics

