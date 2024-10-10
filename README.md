# Call Center Optimization
This project is part of the SkyHack 2.0 Hackathon, where the objective is to analyze customer call center data and propose solutions to optimize Average Handle Time (AHT), improve customer service, and enhance overall call center efficiency. The analysis focuses on understanding call reasons, handling peak hours, and proposing improvements to self-service IVR systems.

---

## **Project Overview**

The main deliverables of the project are:

1. **Long Average Handle Time (AHT) Analysis**:
   - We explored the factors contributing to extended call durations, such as agent performance, call types, and customer sentiment.
   - Identified key drivers of long AHT and AST, especially during high volume call periods.
   - Quantified the percentage difference between the average handling time for the most frequent and least frequent call reasons to identify optimization opportunities.

2. **Self-Solvable Issues Escalation**:
   - We observed a significant portion of calls related to self-solvable issues unnecessarily escalating to agents, increasing their workload.
   - Using transcript and call reason analysis, we identified granular recurring problems that could be resolved via self-service options in the IVR system.
   - Proposed specific IVR improvements to reduce agent intervention, backed by data-driven recommendations.

3. **Understanding Primary Call Reasons**:
   - Analyzed the dataset to uncover patterns that helped categorize primary call reasons.
   - This categorization enables the call center to streamline processes, reduce manual tagging efforts, and ensure customers are directed to the appropriate resources.
   - Optional task: A classification model was built to predict `primary_call_reason` for missing values in the dataset, utilizing NLP and clustering techniques.

---

## **Installation Instructions**

To run this project locally, follow the steps below:

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/ZosTera2438/sky-hack.git

2. Save CSV files on which analysis will be performed in root folder.

4. **Install the Required Packages:**
   Ensure you have Python installed and run the following command to install the necessary dependencies:
   ```bash
   pip install -r requirements.txt
   ```
   Libraries used in this project include:
   
   - `pandas`
   - `numpy`
   - `scikit-learn`
   - `matplotlib`
   - `seaborn`
   - `wordcloud`

5. **Run the Notebook:**
  Launch the notebook with the following command:
   ```bash
   jupyter notebook sky_hack.ipynb
   ```
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
   Identified 93.24% of calls that could be handled by self-service options in the IVR system, such as flight status, booking updates, or cancellations.
   Suggested improvements to the IVR flow to minimize escalations to human agents for simple, self-solvable issues.

---

## Data Dictionary:

| **Column Name**               | **Description**                                             |
| ----------------------------- | ----------------------------------------------------------- |
| `call_id`                     | Unique identifier for each call                             |
| `customer_id`                 | Unique identifier for the customer                          |
| `agent_id`                    | Unique identifier for the agent handling the call           |
| `call_start_datetime`         | Date and time of the call                                   |
| `agent_assigned_datetime`     | Date and time of when agent answered the call               |
| `call_end_datetime`           | Date and time of the call ending                            |
| `customer_name`               | Name of the customer                                        |
| `mp_status`                   | Customer loyalty status (NaN, 0, 1, 2, 3, 4, 5)            |
| `agent_tone`                  | Detected tone of the agent (score from 0 to 5)              |
| `customer_tone`               | Detected tone of the customer (score from 0 to 5)           |
| `average_sentiment`           | Sentiment score of the conversation (range: -1 to 1)        |
| `silence_percent_average`     | Average percentage of silence in calls                      |
| `call_transcript`             | Full transcript of the call conversation                    |
| `primary_call_reason`         | Detected primary reason for the call                        |

---

## Source Code

Jupyter Notebook is used to perform analysis on the given data, **sky_hack.ipynb** file contains source code with outputs.
- calls.csv - https://uc.hackerearth.com/he-public-data/callsf0d4f5a.csv
- customers.csv - https://uc.hackerearth.com/he-public-data/customers2afd6ea.csv
- reason.csv - https://uc.hackerearth.com/he-public-data/reason18315ff.csv
- sentiment_statistics - https://uc.hackerearth.com/he-public-data/sentiment_statisticscc1e57a.csv
  
---

## Test.csv

To handle the missing primary_call_reason values, a classification model was built based on the cleaned and clustered call data. The **Test.csv** file contains predicted the missing primary_call_reason values for 5157 entries.

---

## Presentation

A slide deck summarizing our analysis, insights, and recommendations is included in the repository as **sky_hack_presentation.pdf**.

