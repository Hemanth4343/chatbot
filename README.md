# chatbot
import nltk
import random
nltk.download('punkt')
responses = {
    'greeting': ['Hello', 'Hi there', 'Hey', 'Nice to meet you'],
    'farewell': ['Goodbye', ' See you later', 'Bye', 'Have a great day'],
    'thankful': ['YOu\'re welcome', 'No problem','Anytime']
    }
key_respones = {
    'how are you' : ['I\'m good, 'thank you', 'Feeling great','Not too bad','I\'m doing well. what about you?']
    'thank you' : responses['thankful'],
    'bye': responses['farewell'],
    'hello': responses['greeting']
    }
print("Bot: Hello!(type ' exit ' to end the conversation)")
while True:
    user = input("You: ").lower()
    if user == 'exit':
        print("Bot: Goodbye!")
        break
    responses = "I'm sorry,I didn't understand that."
    for word in nltk,word_tokenize(user):
        if word in key_responses:
            responses = random.choice(key_responses[word])
            break
    print("Bot:",responses)
