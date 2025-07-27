Legal Sentiment Analyzer
## Overview
The Legal Sentiment Analyzer is a Python script (legal_sentiment_analyzer.py) designed to perform sentiment analysis on legal texts, such as court documents, contracts, or other legal documents. It leverages the Google FLAN-T5 model from the transformers library to classify the sentiment of text segments as Positive, Negative, or Neutral. The script processes input files (text or CSV), preprocesses the text, analyzes sentiment at the sentence level, and generates a summary of the results.

## Features

Preprocessing: Cleans whitespace and masks sensitive information (e.g., dates, names).
Sentence-Level Analysis: Splits texts into sentences for granular sentiment analysis using nltk.
Sentiment Classification: Uses the Google FLAN-T5 model to classify sentiments.
Input Support: Accepts .txt files for raw text or .csv files with a text column.
Output: Generates a CSV file (sentiment_analysis_results.csv) with sentiment results and provides a summary of sentiment distribution.
Insights: Offers observations on the overall tone of the document.

## Prerequisites
To run this project, you need:

Python: Version 3.6 or higher
Required Libraries:
pandas
transformers
nltk
torch (required by transformers for the FLAN-T5 model)


NLTK Data: The punkt package for sentence tokenization (downloaded automatically by the script).

## Installation

Clone the repository:
git clone https://github.com/your-username/legal-sentiment-analyzer.git
cd legal-sentiment-analyzer


(Optional but recommended) Create and activate a virtual environment:
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate


## Install dependencies:
pip install -r requirements.txt

The requirements.txt file includes:
pandas
transformers
nltk
torch


The script automatically downloads the required NLTK punkt package on the first run.


## Usage

Prepare your input file:

Text file (.txt): A single file containing the legal text to analyze.
CSV file (.csv): A CSV file with a text column containing legal texts.


## Run the script:
python legal_sentiment_analyzer.py


Enter the path to your input file when prompted (e.g., input_data.csv or document.txt).

## The script will:

Process the input file.
Save results to sentiment_analysis_results.csv.
Display a summary of sentiment distribution and key observations.
Show a sample of the first five analyzed segments.



Example
python legal_sentiment_analyzer.py
Enter the path to the legal document (text or CSV): "C:\Users\shiba\Downloads\Legal_Agreement_Template.txt"

## Input

A CSV file (input_data.csv) with a text column containing legal texts, or a text file (document.txt) with raw legal text.

## Output

A CSV file (sentiment_analysis_results.csv) with columns:
text: The sentence or text segment.
sentiment: The classified sentiment (Positive, Negative, or Neutral).


A console summary, e.g.:Sentiment Analysis Summary:
Total Segments Analyzed: 50
Positive Segments: 10 (20.0%)
Negative Segments: 15 (30.0%)
Neutral Segments: 25 (50.0%)

## Key Observations:
- The document maintains a balanced or neutral tone, with no strong positive or negative bias.

## Sample Results (first 5 segments):
text                                              sentiment
Soumyadeep won the case with strong evidence.       Positive
The ruling was contested by Anapaneya.              Negative
The contract terms were standard.                   Neutral
12/05/2025 marked the appeal deadline.              Neutral
Rahul expressed concerns over the verdict.          Negative



## Project Structure
legal-sentiment-analyzer/
├── legal_sentiment_analyzer.py  # Main script for sentiment analysis
├── README.md                   # This file
├── requirements.txt            # List of dependencies
├── input_data.csv              # Example input file (not included)
└── sentiment_analysis_results.csv  # Output file (generated after running)

## Notes

Performance: The FLAN-T5 model is computationally intensive. Ensure sufficient memory and processing power (GPU recommended for faster inference).
Input Format: CSV files must have a text column. Text files are treated as a single document.
Sensitive Data: The script masks dates (e.g., 12/31/2023 as [DATE]) and names (e.g., John Smith as [NAME]) during preprocessing.
Error Handling: The script checks for file existence and valid CSV format, providing appropriate error messages.

## Contributing
Contributions are welcome! To contribute:

## Contact

For questions or feedback, open an issue on GitHub or contact shibambanik0@gmail.com.
