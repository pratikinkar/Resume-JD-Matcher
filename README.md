# AI-Powered Resume-JD Matcher

An NLP pipeline that scores how well a set of resumes match a given job
description, replicating the core logic behind ATS (Applicant Tracking
System) keyword/relevance matching.

## Overview

1. **Text extraction:** pulls raw text from PDF resumes using PyPDF2.
2. **Preprocessing:** cleans and normalizes text with NLTK — lowercasing,
   special-character removal, stopword removal, and lemmatization.
3. **Vectorization:** represents the job description and each resume as
   TF-IDF vectors.
4. **Matching:** ranks resumes against the job description using cosine
   similarity between vectors.

## Tech Stack

Python · NLTK · Scikit-learn (TF-IDF, cosine similarity) · PyPDF2

## How to Run

1. Install dependencies: `pip install -r requirements.txt`
2. Create a `resumes/` folder in the project root and add PDF resumes to it.
3. Run the notebook. When prompted, paste in the job description text you
   want to match resumes against.
4. The notebook prints a similarity score (0–1) for each resume — higher
   scores indicate closer alignment with the job description.

## Example Output

```
resume_a.pdf: 0.22
resume_b.pdf: 0.15
resume_c.pdf: 0.11
```

## Limitations & Next Steps

TF-IDF is a keyword-frequency method — it has no semantic understanding, so
it won't recognize that "salary" and "compensation" are related concepts.
A natural extension is to swap TF-IDF for sentence embeddings (e.g. via
`sentence-transformers` / Hugging Face) for semantic, rather than purely
lexical, matching.

## Author

**Pratik Inkar**
[LinkedIn](https://www.linkedin.com/in/pratikinkar/) · [GitHub](https://github.com/pratikinkar)

