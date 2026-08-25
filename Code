import ollama

MODEL = "llama3.2"

def chat():
    print("Chatbot: Hi! I am Jackbot version 5.0. Type 'quit' to exit.")
    
    messages = []  # this holds the full conversation history

    while True:
        user_input = input("You: ")
        if user_input.lower().strip() in ("quit", "exit", "bye"):
            break

        # add the user's message to history
        messages.append({"role": "user", "content": user_input})

        print("Chatbot: ", end="", flush=True)
        stream = ollama.chat(
            model=MODEL,
            messages=messages,   # send the whole history, not just this message
            stream=True
        )

        full_response = ""
        for chunk in stream:
            content = chunk["message"]["content"]
            print(content, end="", flush=True)
            full_response += content
        print()  # newline after response finishes

        # add the assistant's reply to history too
        messages.append({"role": "content" if False else "content", "content": full_response})

if __name__ == "__main__":
    chat()
