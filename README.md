# Summary of Code in AJCreplica.ipynb

This code appears to be a Python script that performs various data processing tasks on datasets related to government programs. Here's a high-level overview of what the code does:

## Importing Libraries ##
The script starts by importing various Python libraries for tasks such as handling PDFs, data manipulation, text processing, and machine learning. Some of the libraries used include `io`, `requests`, `pandas`, `numpy`, `sklearn`, and others.

## Uploading & Clean-Up ##
### BIL Data ###
1. It fetches a CSV file from the White House website (BIL data) using the `requests` library.
2. The script renames and cleans up columns in the BIL data.
3. It maps agency names to abbreviations and updates the 'agencyId' column accordingly.
4. It updates eligibility information in the 'eligibilityId' column based on a predefined dictionary.
5. It removes unnecessary columns from the BIL dataset.

### IRA Data ###
1. Similar to BIL, it fetches a CSV file from the White House website (IRA data).
2. Renames and cleans up columns in the IRA data.
3. Maps agency names to abbreviations and updates the 'agencyId' column.
4. Updates eligibility information in the 'eligibilityId' column based on a predefined dictionary.
5. Removes unnecessary columns from the IRA dataset.

### Combined Datasets ###
The script combines the cleaned BIL and IRA datasets into a single dataset called 'combined.'

## NLP Multiclass Text Classification ##
The script performs Natural Language Processing (NLP) for text classification using machine learning. It uses a labeled dataset ('ajcDf') containing 'category' and 'description' columns.

1. Text preprocessing and cleaning are applied to the 'ajcDf' dataset.
2. The text data is transformed into numerical features using Term Frequency-Inverse Document Frequency (TF-IDF) vectorization.
3. A Multinomial Naive Bayes classifier is trained on the TF-IDF features for text classification.
4. The model is applied to predict categories for descriptions in the 'combined' dataset.
5. Category labels are mapped to more human-readable labels.

## Missing Links ##
The script attempts to find missing links ('NaN' values) in the 'link' column of the 'combined' dataset by performing Google searches based on agency, bureau, and program names. It updates the 'link' column with the first Google search result.

## Filtering Justice40 Programs ##
The script filters and extracts programs that are related to Justice40 from the 'combined' dataset by matching agency and program names based on partial string matching and fuzzy matching.

## To-Do & Updates ##
This section includes comments outlining future improvements and tasks to be addressed in the code.

Please note that the script involves data manipulation, text classification, and data enrichment tasks, primarily related to government programs and their descriptions.
If you have any questions, please do not hesistate to reach out via email: unosia@ncsu.edu
