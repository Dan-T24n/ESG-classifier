# Summary

Analyze ESG reports and classify each page into 3 categories: environmental, social, governance.

# Data

Each report is a pdf file. Each page is a record. There are about 2000 pages and 50 reports.

- parsing pdf: important step, some pages are not parse correctly due to charts, graphics, etc.
- improve parsing with OCR could help, but too slow (10s/page)

Data folder is not tracked for data privacy.

# Code

- EDA: parse pdf, preprocess text, tokenization for analysis
- Model 1: extract embeddings with `sentence-transformers`, using FinBERT-ESG and sentence-roberta
- Model 2: fine-tuning FinBERT for classification directly

# Results

- Extract embeddings seems to work, performance is sensitive to parameters tuning of the classifier.

- Fine-tuning FinBERT directly is not as good as expected. Big improvement if ensemble multiple instances through cross-validation.
