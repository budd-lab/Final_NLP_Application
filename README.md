**Capstone Project**

**Legal Contracts Clause Extraction and Classification Final Report**

**1.	Define the Problem Statement:**

Legal contracts run businesses and unstructured data form the backbone of business operations, capturing critical business information, obligations, and risks. Manual review of contracts is time-intensive and prone to errors. By automating this process, businesses can reduce the time and cost of contract review and minimize risks by consistently identifying and addressing key contractual clauses. This will also empower non-legal personnel with tools to quickly understand contract obligations. This analysis could help bridge the gap between AI tools and real-world usability, translating complex legal documents into actionable insights that can be understood and leveraged by diverse stakeholders.

This problem aims to automate the extraction and classification of key clauses and obligations from legal contracts. Build an NLP model capable of extracting specific legal clauses, categorizing them into predefined types and summarizing. This will enable efficient analysis of large volumes of unstructured data and contracts into digestible input for the legal team's review and decision-making.


**2.	Model Outcomes or Predictions**: As the legal contracts data is labeled, classification models will be used. Supervised learning algorithms will be used as data is labeled into specific legal clause types. Expected output of the selected model will be to predict legal clause on unseen data and eventually apply that on any type of legal document to classify legal clauses and minimize business risk exposure. 

**3.	Data Acquisition**: Data is acquired from 350 different datasets from Kaggle. These 350 separate legal documents contain 350+ different legal clauses and 150,000 total examples. All the 350 datasets are combined to build classification models and anomaly detection. Due to significant processing time, only 5% of the dataset was used to train and test the model that included more than 7,000 records.

**4.	Data Preprocessing/Preparation**: 

**a) Preprocessing**: Steps taken for text preprocessing:
  - Tokenization: Splitting text into tokens using NLTK.
  - Stopword Removal: Filtering out common words like "the", "and", etc.
  - Stemming: Reducing words to their base forms using PorterStemmer.
  - Lemmatization: Further normalization for meaningful word forms.

**b) Feature Extraction**: TF-IDF Vectorization:
  - Transformed processed text into numerical features.
  - Limited to the top 5,000 features to balance model complexity and performance.
  - Train-Test Split: (Training Data: 80% and Test Data: 20%)

**5.	Modeling**: Classifiers Used - Random Forest Classifier, SVM, and MultinomialNB.

**6.	Model Evaluation**: SVM classifier yielded the highest accuracy across three differenct classifiers using GridSearchCV: 

a) RandomForest 
  - Best Parameters: {'max_depth': None, 'min_samples_split': 2, 'n_estimators': 200}
  - Accuracy: 0.612989

b) SVM
  - Best Parameters: {'C': 10, 'gamma': 'scale', 'kernel': 'linear'}
  - Accuracy: 0.638834

c) MultinomialNB 
  - Best Parameters: {'alpha': 0.5} )
  - Accuracy: 0.463883

**Insights from Feature Importance**: Top features contributing to predictions:
  1) agreement
  2) shall
  3) term
  4) company
  5) parti

**Example Inference A new clause was tested:**
  1) Clause: "The supplier must deliver the goods within 30 days of receiving the purchase order."
  2) Predicted Label: good-reason
  3) This demonstrates the model's ability to classify clauses accurately for the sample example.

**7.	Conclusion and Next steps:**

**a)	Strengths:**
  1) The pipeline effectively preprocesses and classifies legal clauses.
  2) Visualizations provide useful insights into data distribution and model performance.

**b)	Areas for Improvement:**
  1) Handle class imbalances using techniques like oversampling or class weights.
  2) Explore advanced models for better clause classification.

**c)	Next Steps:**
  1) Assess other classifiers to test model performance.
  2) Explore clause summarization for AI insights
