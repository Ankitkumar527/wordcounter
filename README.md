# wordcounter
def word_counter(text):
    # Convert the text to lowercase to make the counting case insensitive
    text = text.lower()
    
    # Remove punctuation from the text
    import string
    text = text.translate(str.maketrans('', '', string.punctuation))
    
    # Split the text into words
    words = text.split()
    
    # Create an empty dictionary to store the word counts
    word_counts = {}
    
    # Iterate over the list of words
    for word in words:
        if word in word_counts:
            word_counts[word] += 1
        else:
            word_counts[word] = 1
            
    return word_counts

# Example usage
if __name__ == "__main__":
    text = "Hello world! Hello everyone. Welcome to the world of Python."
    counts = word_counter(text)
    for word, count in counts.items():
        print(f"{word}: {count}")
