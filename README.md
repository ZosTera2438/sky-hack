# Call Center Optimization
This project is part of the SkyHack 2.0 Hackathon, where the objective is to analyze customer call center data and propose solutions to optimize Average Handle Time (AHT), improve customer service, and enhance overall call center efficiency. The analysis focuses on understanding call reasons, handling peak hours, and proposing improvements to self-service IVR systems.

---

## **Project Overview**

The main objectives of the project are:

1. **Identifying Key Factors for Long AHT:**  
   Analyze agent performance, call types, and customer sentiment to discover the drivers of long AHT and AST (Average Speed to Answer).
   
2. **Clustering Call Transcripts:**  
   Apply Natural Language Processing (NLP) techniques to group similar call transcripts and identify recurring issues.

3. **Optimizing Agent Allocation:**  
   Understand peak hour trends and recommend better agent distribution during high call volume periods to improve efficiency.

4. **Self-Service IVR Enhancement:**  
   Identify self-resolvable issues and propose improvements to the IVR system to handle them, thus reducing unnecessary agent intervention.

---

## **Installation Instructions**

To run this project locally, follow the steps below:

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/ZosTera2438/sky-hack.git

2. **Install the Required Packages:**
   Ensure you have Python installed and run the following command to install the necessary dependencies:
   ```bash
   pip install -r requirements.txt

Libraries used in this project include:

- **pandas**
- **numpy**
- **scikit-learn**
- **matplotlib**
- **seaborn**
- **wordcloud**

3. **Run the Notebook:**
  Launch the notebook with the following command:
   ```bash
   jupyter notebook sky_hack.ipynb

Note: Running the full notebook might take **approximately 20 minutes** due to the complex data processing, clustering, and prediction steps. Please ensure you have sufficient system resources for the execution.

---

## Approach and Methodology

1. **Data Preprocessing:**
Cleaned and tokenized the call transcripts for NLP analysis.
Handled missing values, specifically predicting primary_call_reason for unlabeled records.
Generated features like average sentiment, call duration, and customer-agent tone to assist in analysis.

2. **Clustering and NLP Analysis:**
Used TF-IDF (Term Frequency-Inverse Document Frequency) to extract important terms from the call transcripts.
Applied K-Means clustering to group calls into categories based on their transcript content.
Key clusters emerged around issues like flight changes, refunds, delays, and baggage problems.

3. **Sentiment and Tone Analysis:**
Extracted agent and customer sentiment to gauge the emotional state of interactions.
Analyzed the correlation between negative sentiment and extended call durations.

4. **Peak Hour Analysis for Agent Allocation:**
Studied call volume trends to detect high-volume periods and suggested increasing agent staffing during peak times (e.g., morning hours, weekends).
Dynamic agent allocation could reduce AHT during peak times by matching agent availability with customer demand.

5. **Self-Service IVR Recommendations:**
Identified 14.77% of calls that could be handled by self-service options in the IVR system, such as flight status, booking updates, or cancellations.
Suggested improvements to the IVR flow to minimize escalations to human agents for simple, self-solvable issues.

---

## Test File Prediction

To handle the missing primary_call_reason values, a classification model was built based on the cleaned and clustered call data. The **Test.csv** file contains predicted the missing primary_call_reason values for 5157 entries.

---

## Presentation

A slide deck summarizing our analysis, insights, and recommendations is included in the repository as **sky_hack_presentation.pptx**.

