
 
### Objective
The "Caused-by Prediction System Based on Tickets" project aims to revolutionize the IT support landscape by implementing an advanced ticket classification system powered by Large Language Models (LLMs). This innovative system is designed to enhance the efficiency of IT support teams by streamlining the handling of tickets and requests. Its primary function is to ensure accurate routing of tickets to the correct department, thereby accelerating issue resolution and preventing misdirection of requests.

In enterprise environments, the classification of the 'caused-by' factor for incidents, which involves various attributes such as short description and sub-category, presents a significant challenge due to its high-scale nature, with the number of classes reaching up to 100,000 causes or sub-categories. This complexity necessitates a comprehensive approach that includes a combination of dimensionality reduction, natural language processing (NLP), machine learning, and optimization techniques.

One of the critical sub-problems addressed by this system is the prediction of the assignment group to which an incident belongs, followed by the identification of the top 5 or 10 possible causes among the thousands of 'caused-by' labels. This approach not only improves the classification accuracy but also enhances the reliability and trustworthiness of the system in the eyes of customer service agents, through effective storytelling and demonstration of its capabilities.

### DATASET:

The data set is collected from Kaggle.
https://www.kaggle.com/datasets/venkatasubramanian/automatic-ticket-classification

### Implementation

#### Traditional NLP Model Implementation:
  The models adhere to the standard classification framework. Features are processed into a combined input feature of Complaints as a sparse matrix, with Products as the target variable. Further employed Random Forest, an ensemble technique that builds an additive model by minimizing the loss function's expected value. It refines predictions using a series of weak learners, typically decision trees, ensuring high accuracy and efficiency in various tasks.

#### BERT Large Language Model Implementation:
  This involves fine-tuning of a BERT-based-uncased model from Hugging Face to enhance AUC and classification performance. Due to computational resource limitations, we retrained the model on a modified dataset with 5 instead of 17 categories. This was done using Google Colab Pro with a T4 GPU, utilizing 96.4 compute units and taking 3 hours of total training time. The model, pre-trained with 7 billion parameters, was specifically chosen for sequence classification from the TensorFlow Python library. It was pre-trained on a corpus of 11,038 unpublished books and English Wikipedia. The model underwent 30 epochs of training with negligible observed loss.
  
### Classes

There are 5 different classes available in the target variable. They are listed below.
•	Credit card or prepaid card

•	Checking or savings account

•	Mortgage

•	Credit reporting, credit repair services, or other personal consumer reports

•	Credit card

•	Bank account or service

•	Debt collection

### Results

BERT has demonstrated a 7% improvement in accuracy and performance compared to Logistic Regression. One of the key advantages of BERT is its ability to understand context by analyzing the entire input text. This contextual understanding is particularly beneficial for accurately classifying IT tickets, which often contain nuanced language. Additionally, BERT's capability to capture semantic representations of words and phrases enables the model to grasp the meaning behind the text, a critical aspect for managing IT tickets where terms may have different implications based on context.

However, BERT models are computationally demanding in terms of both training and inference. In contrast, Logistic Regression is a simpler model that is more computationally efficient. BERT requires significant resources, including powerful GPUs, for effective training and inference, while Logistic Regression has lower resource requirements.

In summary, while BERT Language Models offer superior performance in IT ticket classification through their contextual understanding and semantic representations, they pose computational challenges.
