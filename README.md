# chatbot
import nltk
import random
nltk.download('punkt')
responses = {
    'greeting': ['Hello', 'Hi there', 'Hey', 'Nice to meet you'],
    'farewell': ['Goodbye', 'See you later', 'Bye', 'Have a great day'],
    'thankful': ['You\'re welcome', 'No problem', 'Anytime']
}
key_responses = {
    'how are you': ['I\'m good, thank you', 'Feeling great', 'Not too bad', 'I\'m doing well. How about you?'],
    'thank you': responses['thankful'],
    'bye': responses['farewell'],
    'hello': responses['greeting']
}
print("Bot: Hello!(Type 'exit' to end the conversation)")

while True:
    user = input("You: ").lower()
    if user == 'exit':
        print("Bot: Goodbye!")
        break
    response = "I'm sorry, I didn't understand that."
    for word in nltk.word_tokenize(user):
        if word in key_responses:
            response = random.choice(key_responses[word])
            break
    print("Bot:", response)
