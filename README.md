# Web-Scraping-and-Text-Analysis
This Python code performs web scraping of URLs and analyzes the text content using various text analysis techniques. It utilizes the following libraries: pandas, BeautifulSoup, requests, and nltk. The output is given in excel file with analysis for each url.

# Usage 
Set up the input data:

Ensure you have a DataFrame df with columns URL_ID and URL containing the URLs to scrape.
Modify the range in the for loop to specify the number of URLs to scrape (currently set to 10).
Execute the code:

Run the script in a Python environment or execute each code block individually.
Output:

The code generates text files and stores them with names name.txt, where name is a number based on the iteration.
The text files are preprocessed to remove stop words based on various word files.
The code calculates several text analysis metrics, such as positive and negative scores, polarity score, subjectivity score, average sentence length, percentage of complex words, FOG index, average words per sentence, complex word count, word count, syllables per word, and count of personal pronouns.
The results are stored in the output_df DataFrame, which can be further processed or exported as desired.


# Metrics 
Positive Score: This score is calculated by assigning the value of +1 for each word if found in the Positive Dictionary and then adding up all the values.

Negative Score: This score is calculated by assigning the value of -1 for each word if found in the Negative Dictionary and then adding up all the values. We multiply the score with -1 so that the score is a positive number.

Polarity Score: This is the score that determines if a given text is positive or negative in nature. It is calculated by using the formula: 
Polarity Score = (Positive Score – Negative Score)/ ((Positive Score + Negative Score) + 0.000001)

Subjectivity Score: This is the score that determines if a given text is objective or subjective. It is calculated by using the formula: 
Subjectivity Score = (Positive Score + Negative Score)/ ((Total Words after cleaning) + 0.000001)


Analysis of Readability
Analysis of Readability is calculated using the Gunning Fox index formula described below.
Average Sentence Length = the number of words / the number of sentences
Percentage of Complex words = the number of complex words / the number of words 
Fog Index = 0.4 * (Average Sentence Length + Percentage of Complex words)

Average Number of Words Per Sentence
Average Number of Words Per Sentence = the total number of words / the total number of sentences

Complex Word Count
Complex words are words in the text that contain more than two syllables.

Word Count
We count the total cleaned words present in the text by 
removing the stop words (using stopwords class of nltk package).
removing any punctuations like ? ! , . from the word before counting.

Syllable Count Per Word
We count the number of Syllables in each word of the text by counting the vowels present in each word. We also handle some exceptions like words ending with "es","ed" by not counting them as a syllable.

Personal Pronouns
To calculate Personal Pronouns mentioned in the text, we use regex to find the counts of the words - “I,” “we,” “my,” “ours,” and “us”. Special care is taken so that the country name US is not included in the list.

Average Word Length
Average Word Length is calculated by the formula:
Sum of the total number of characters in each word/Total number of words
