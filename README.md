Legal Sentiment Analyzer
Overview
The Legal Sentiment Analyzer is a Python script (legal_sentiment_analyzer.py) designed to perform sentiment analysis on legal texts, such as court documents, contracts, or other legal documents. It uses the Google FLAN-T5 model from the transformers library to classify the sentiment of text segments as Positive, Negative, or Neutral. The script processes input files (text or CSV), preprocesses the text, analyzes sentiment at the sentence level, and generates a summary of the results.
Features

Preprocesses legal texts by cleaning whitespace and masking sensitive information (e.g., dates, names).
Splits texts into sentences for granular sentiment analysis using nltk.
Uses the Google FLAN-T5 model for sentiment classification.
Supports input in .txt or .csv formats (CSV must have a text column).
Outputs results to a CSV file (sentiment_analysis_results.csv) and provides a summary of sentiment distribution.
Provides insights into the overall tone of the document.

Prerequisites
To run this project, you need:

Python 3.6 or higher
Required Python libraries:
pandas
transformers
nltk
torch (required by transformers for the FLAN-T5 model)


NLTK data (punkt for sentence tokenization, downloaded automatically by the script)

Installation

Clone the repository:
git clone https://github.com/your-username/legal-sentiment-analyzer.git
cd legal-sentiment-analyzer


(Optional but recommended) Create and activate a virtual environment:
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate


Install dependencies:
pip install pandas transformers nltk torch


The script automatically downloads required NLTK data (punkt) on the first run.


Usage

Prepare your input file:
Text file (.txt): A single file containing the legal text to analyze.
CSV file (.csv): A CSV file with a text column containing legal texts.


Run the script:python legal_sentiment_analyzer.py


Enter the path to your input file when prompted (e.g., input_data.csv or document.txt).
The script will:
Process the input file.
Save results to sentiment_analysis_results.csv.
Display a summary of sentiment distribution and key observations.
Show a sample of the first five analyzed segments.



Example
python legal_sentiment_analyzer.py
Enter the path to the legal document (text or CSV): input_data.csv

Input:

A CSV file (input_data.csv) with a text column containing legal texts, or a text file (document.txt) with raw legal text.Output:
A CSV file (sentiment_analysis_results.csv) with columns text (sentence) and sentiment (Positive, Negative, or Neutral).
A console summary, e.g.:Sentiment Analysis Summary:
Total Segments Analyzed: 50
Positive Segments: 10 (20.0%)
Negative Segments: 15 (30.0%)
Neutral Segments: 25 (50.0%)

Key Observations:
- The document maintains a balanced or neutral tone, with no strong positive or negative bias.

Sample Results (first 5 segments):
text                                              sentiment
[NAME] won the case with strong evidence.         Positive
The ruling was contested by [NAME].               Negative
The contract terms were standard.                 Neutral
[DATE] marked the appeal deadline.               Neutral
[NAME] expressed concerns over the verdict.       Negative



Project Structure
legal-sentiment-analyzer/
├── legal_sentiment_analyzer.py  # Main script for sentiment analysis
├── README.md                   # This file
├── requirements.txt            # List of dependencies
├── input_data.csv              # Example input file (not included)
└── sentiment_analysis_results.csv  # Output file (generated after running)

requirements.txt
To simplify dependency installation, you can create a requirements.txt file:
pandas
transformers
nltk
torch

Install using:
pip install -r requirements.txt

Notes

Performance: The FLAN-T5 model is computationally intensive. Ensure you have sufficient memory and processing power (GPU recommended for faster inference).
Input Format: CSV files must have a text column. Text files are treated as a single document.
Sensitive Data: The script masks dates (e.g., 12/31/2023 as [DATE]) and names (e.g., John Smith as [NAME]) during preprocessing.
Error Handling: The script checks for file existence and valid CSV format, with appropriate error messages.

Contributing
Contributions are welcome! To contribute:

Fork the repository.
Create a new branch (git checkout -b feature-branch).
Make your changes and commit (git commit -m "Add feature").
Push to the branch (git push origin feature-branch).
Open a Pull Request.

License
This project is licensed under the MIT License. See the LICENSE file for details.
Contact
For questions or feedback, open an issue on GitHub or contact [Your Name] at [your.email@example.com].
