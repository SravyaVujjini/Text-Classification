# Text-Classification

The main objective is to implement a binary classifier to distinguish healthcare companies from non-healthcare ones based on the textual content. By utilizing a dataset containing pure healthcare companies and a mixed unlabeled set of healthcare and non-healthcare entities, our goal is to first extract non-health care data from the mixed unlabelled data and then create a model that can effectively categorize companies into these two distinct domains.

### *Preprocessing*

Medical terms in rows of healthcare_only.csv are sparse and cannot contribute to the labeling of data in half_healthcare.csv in several of my experiments. Explored methods
*   Based on keyword frequency
*   Based on similariy between every 'text' row of 2 csv documents
*   By creating concentrated healthcare data (implemented solution)
*   Created data concentrated with medical terminology by joining text from all the rows of healthcare_only.csv and removing stopwords.
*   This consolidated representation emphasizes the distinctive vocabulary of the healthcare related documents.
*   The idea is that the unique terminology and language patterns specific to healthcare will stand out, allowing for the identification of non health care companies based on the dissimilarity of the language

### *Healthcare and non-healthcare data detection*

- Vectorized the sentences in each row.\
- Calculated similarity score between row with healthcare terms and all the rows from half_healthcare.csv\
- Set the median of similarity score as threshold to separate healthcare and non-healthcare rows.
- 

### *Model finetuning*

Finetuned the pretrained 'DistilBERT' model by traning for 3 epochs. 
