Jackbot
A simple terminal chatbot built with Ollama, running locally against the llama3.2 model. Jackbot keeps full conversation history so it has memory of earlier turns in the session, and streams responses token-by-token as they're generated.
Requirements
Python 3.8+
Ollama installed and running locally
The llama3.2 model pulled:
bash
  ollama pull llama3.2
Setup
bash
pip install -r requirements.txt
Usage
bash
python jackbot.py
Type your messages and press Enter. Type quit, exit, or bye to end the session.
How it works
Each user message is appended to a running messages list along with the assistant's replies, so the full conversation is sent to the model on every turn.
Responses are streamed via ollama.chat(..., stream=True) and printed as each chunk arrives.
