# 🤖 NewsBot Intelligence System
**ITAI 2373 Mid-Term Project** (individual submission by Kristina Akpan)

**Repository:** https://github.com/bookwithkai2/ITAI2373-NewsBot-Midterm

An end to end NLP system that reads news articles and automatically classifies them, extracts the people, organizations, places, dates and money they mention, measures their sentiment and emotional tone, and parses who did what to whom. Built on 2,000 real BBC News articles with spaCy, NLTK and scikit-learn, and designed to run on the Google Colab free tier.

## 👤 Author
**Kristina Akpan** (individual submission; I was not assigned to a group, so I completed every module myself)

### My Contributions
* **Module 1:** business case, target users and value proposition
* **Module 2:** preprocessing pipeline with contraction handling, unicode normalization and edge case tests
* **Module 3:** TF-IDF parameter optimization, category term analysis, word clouds and chi squared feature importance
* **Module 4:** POS profiles by category, Kruskal Wallis significance tests and POS trigram patterns
* **Module 5:** dependency parsing, syntactic complexity features and a semantic role extractor (23,440 event frames)
* **Module 6:** title, article and sentence level sentiment plus a seven emotion lexicon
* **Module 7:** four classifiers on two feature sets, grid search, feature selection and error analysis
* **Module 8:** entity analysis, cross category patterns, co-occurrence network and entity sentiment
* **Integration:** the NewsBotIntelligenceSystem class, testing on new articles, README and reflective journal

AI assistance was used as a coding and writing aid, as permitted by the assignment instructions.

## 📊 Key Results
| Area | Result |
|:---|:---|
| Classification | Tuned linear SVM, **96.75% test accuracy** (98.3% 5 fold CV), macro F1 0.967 |
| Model comparison | SVM and Logistic Regression beat Naive Bayes and Random Forest; TF-IDF tuning added about 1 point of accuracy |
| Sentiment | Entertainment is the most positive category, Politics the most negative (and has the most negative headlines) |
| Writing style | Business is number heavy, Entertainment and Sports are name heavy, Politics has the longest and most complex sentences |
| NER | 82,803 entities extracted; co-occurrence network and entity level sentiment for reputation tracking |
| Semantic roles | 23,440 agent, action, patient event frames extracted from dependency parses |

## 🧩 Modules Covered
1. **Real world application:** business case, users, value proposition
2. **Preprocessing:** cleaning, contractions, unicode, tokenization, stop words, lemmatization
3. **TF-IDF:** parameter optimization, category terms, word clouds, chi squared feature importance
4. **POS tagging:** category style profiles, statistical tests, POS trigram patterns
5. **Syntax and semantics:** dependency parsing, complexity features, semantic role frames
6. **Sentiment and emotion:** VADER at title, article and sentence level plus an emotion lexicon
7. **Classification:** 4 algorithms x 2 feature sets, grid search, feature selection, error analysis
8. **NER:** entity statistics, cross category patterns, relationship network, entity sentiment

## 📁 Folder Structure
```
ITAI2373-NewsBot-Midterm/
├── NewsBot_Intelligence_System_KristinaAkpan.ipynb   # complete notebook with all outputs
├── newsbot_dataset.csv                 # prepared 2,000 article dataset (created by the notebook)
├── NewsBot_Reflection_KristinaAkpan.pdf # 2 page reflective journal
└── README.md
```

## ▶️ How to Run
1. Open the notebook in Google Colab (File, Upload notebook, or open from GitHub).
2. Run all cells (Runtime, Run all). The first cell installs spaCy, NLTK data and the other libraries.
3. The dataset downloads automatically from a public copy of the original BBC News corpus. To use the Kaggle copy instead, upload BBC News Train.csv from the [Learn AI BBC competition](https://www.kaggle.com/competitions/learn-ai-bbc/data) and the loader will pick it up.
4. A full run takes roughly 10 to 15 minutes on the free CPU runtime (spaCy parsing and the grid search take the longest).

### Try your own article
```python
result = newsbot.process_article("Your headline", "Your article text ...")
result['predicted_category'], result['sentiment']['sentiment_label'], result['entities']
```

## 📚 Dataset
BBC News corpus (D. Greene and P. Cunningham, "Practical Solutions to the Problem of Diagonal Dominance in Kernel Document Clustering", ICML 2006): 2,225 articles from 2004 to 2005 in five categories (business, entertainment, politics, sport, tech). This is the source of the Kaggle competition recommended in the assignment. I used the cased version with headlines because NER and POS tagging depend on capitalization.

## ⚠️ Limitations
* Training data is from one outlet and one period (2004 to 2005); there is no Health category, so health stories are flagged as low confidence.
* The small spaCy model makes some type errors (for example political parties tagged as people).
* Lexicon based sentiment and emotion scores are signals, not ground truth.

## 🎥 Video Demonstration
[Optional: add your video link here]
