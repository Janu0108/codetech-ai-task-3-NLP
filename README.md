# codetech-ai-task-3-NLP

![Uploading WhatsApp Image 2024-08-06 at 8.11.15 PM.png…]()


Load Word Lists: The load_word_lists function returns predefined lists of positive and negative words.
Analyze Sentiment Function: The analyze_sentiment function converts the text to lowercase, splits it into words, and counts the occurrences of positive and negative words. It then determines the sentiment based on the counts.
Main Block: The main block loads the word lists, sets up a sample text, analyzes its sentiment using the function, and prints the result.


1. Loading Word Lists
The first step in this program is to create predefined lists of positive and negative words. This helps to classify the words in the input text as positive or negative.

python
Copy code
def load_word_lists():
    # Predefined lists of positive and negative words
    positive_words = ["good", "happy", "love", "awesome", "excellent", "great", "fantastic", "nice", "amazing"]
    negative_words = ["bad", "sad", "hate", "terrible", "awful", "horrible", "poor", "worse", "worst"]
    return positive_words, negative_words
Positive Words List: Contains words that are generally associated with positive sentiments.
Negative Words List: Contains words that are generally associated with negative sentiments.
2. Analyzing Sentiment
The next step is to analyze the sentiment of the input text based on these predefined word lists.

python
Copy code
def analyze_sentiment(text, positive_words, negative_words):
    # Convert text to lowercase and split into words
    words = text.lower().split()
    
    # Count positive and negative words
    positive_count = sum(1 for word in words if word in positive_words)
    negative_count = sum(1 for word in words if word in negative_words)
    
    # Determine sentiment
    if positive_count > negative_count:
        return "Positive"
    elif negative_count > positive_count:
        return "Negative"
    else:
        return "Neutral"
Convert Text to Lowercase: This ensures that the text comparison is case-insensitive.
Split into Words: The text is split into individual words for analysis.
Count Positive and Negative Words: The program counts how many words from the text appear in the positive and negative word lists.
positive_count: The number of words in the text that match the positive words list.
negative_count: The number of words in the text that match the negative words list.
Determine Sentiment: The sentiment is determined by comparing the counts:
If positive_count is greater than negative_count, the sentiment is "Positive".
If negative_count is greater than positive_count, the sentiment is "Negative".
If both counts are equal, the sentiment is "Neutral".
3. Main Block
The main block of the program ties everything together. It loads the word lists, processes the input text, and prints the sentiment.

python
Copy code
if __name__ == "__main__":
    # Load word lists
    positive_words, negative_words = load_word_lists()
    
    # Sample input text
    text = "I love sunny days but I hate rainy days!"
    
    # Analyze the sentiment
    sentiment = analyze_sentiment(text, positive_words, negative_words)
    
    # Print the result
    print(f"Sentiment of the text: '{text}' is {sentiment}")
Load Word Lists: Calls the load_word_lists function to get the predefined positive and negative words.
Sample Input Text: Defines a sample text string to analyze.
Analyze Sentiment: Calls the analyze_sentiment function with the sample text and the word lists to determine the sentiment.
Print the Result: Outputs the sentiment of the sample text.
Output
When you run the program with the sample input text "I love sunny days but I hate rainy days!", it will output:

sh
Copy code
Sentiment of the text: 'I love sunny days but I hate rainy days!' is Neutral
Limitations
This approach is very basic and has several limitations:

Limited Vocabulary: The predefined lists of positive and negative words are very small and may not cover all possible words that could indicate sentiment.
Context Ignorance: The program does not understand the context of words. For example, it cannot distinguish between "not good" (which is negative) and "good".
No Weighting: All words are treated equally without considering the strength of the sentiment they convey.
Negations: The program does not handle negations well. For example, "not happy" would be incorrectly classified as positive.
![Uploading WhatsApp Image 2024-08-06 at 8.11.14 PM.jpeg…]()

