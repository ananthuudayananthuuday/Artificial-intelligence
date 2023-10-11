# Artificial-intelligence
import nltk
from nltk.chat.util import Chat, reflections

# Define some custom patterns and responses.
custom_patterns = [
    (r'hi|hello|hey', ['Hello!', 'Hi there!']),
    (r'how are you', ['I am just a computer program, so I do not have feelings. How can I assist you?']),
    (r'what is your name', ['I am a chatbot, and you can call me ChatGPT.']),
    (r'bye|goodbye', ['Goodbye!', 'See you later!']),
]

# Define some reflections for personal pronouns.
custom_reflections = {
    "i am": "you are",
    "i was": "you were",
    "i": "you",
    "i'm": "you are",
    "my": "your",
    "you are": "I am",
    "you were": "I was",
    "your": "my",
    "yours": "mine",
    "me": "you"
}

# Create a chatbot with the defined patterns and reflections.
chatbot = Chat(custom_patterns, reflections)

# Main loop to interact with the chatbot.
print("Hello! I'm a simple chatbot. You can type 'bye' to exit.")
while True:
    user_input = input("You: ")
    if user_input.lower() == 'bye':
        print("Chatbot: Goodbye!")
        break
    response = chatbot.respond(user_input)
    print("Chatbot:", response)
