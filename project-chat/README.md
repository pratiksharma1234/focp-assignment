# Chatbot for The British College

This project is a simple chatbot program designed to simulate a conversation between a user and an agent representing The British College of Nepal. The chatbot is capable of providing context-aware responses, maintaining a conversation log, and simulating a typing effect for a more interactive user experience.

## Features
- **Dynamic Agent Name:** The chatbot introduces itself with a randomly chosen name from a predefined list.
- **Time-Based Greeting:** The chatbot greets the user based on the current time of day (morning, afternoon, or evening).
- **Context-Aware Responses:** The chatbot adapts its responses based on the context of the conversation, such as courses or fees.
- **Pattern Matching:** User input is matched against predefined patterns to determine the most appropriate response.
- **Typing Simulation:** Responses are displayed character by character to simulate typing.
- **Chat History:** Users can request to view the chat history during the session.
- **Chat Logging:** The entire chat session is saved to a file named after the user.

## Prerequisites
- Python 3.x
- A JSON file named `responses.json` containing chatbot response data.

### Example `responses.json`
```json
[
    {
        "patterns": ["hello", "hi", "hey"],
        "responses": ["Hello! How can I assist you today?", "Hi there! What can I do for you?", "Hey! How can I help?"]
    },
    {
        "patterns": ["courses", "programs"],
        "responses": ["We offer a variety of courses. Which program are you interested in?", "Our programs include business, IT, and more. Let me know what you're looking for."]
    }
]
```

## How to Run
1. Clone or download the project files.
2. Ensure Python is installed on your system.
3. Place a `responses.json` file in the same directory as the script.
4. Run the script using the command:
   ```bash
   python chatbot.py
   ```

## Code Overview

### 1. **Loading Responses**
The chatbot loads responses from a JSON file using the `load_responses` function. If the file is missing, an error message is displayed, and the program exits.

### 2. **Agent Name Generation**
The `generate_agent_name` function randomly selects a name for the chatbot from a predefined list.

### 3. **Chat Logging**
The `log_session` function saves the conversation to a text file named `chat_log_<username>.txt`.

### 4. **Pattern Matching**
The `match_pattern` function uses regular expressions to check if user input matches any predefined patterns.

### 5. **Typing Simulation**
The `simulate_typing` function displays responses character by character with a small delay to mimic typing.

### 6. **Context Awareness**
The chatbot maintains a `context` variable to provide relevant responses based on the ongoing conversation.

### 7. **Main Chat Function**
The `start_chat` function handles user interaction, processes input, generates responses, and logs the chat session.

## Usage
- Start the chatbot and enter your name.
- Interact with the chatbot by asking questions about courses, fees, or other topics.
- Type "show chat history" to view the conversation so far.
- Type "bye", "quit", or "exit" to end the chat.

## Example Interaction
```
Welcome to the british college chatbot! Please enter your name: John
Good afternoon, John! Welcome to the british college of nepal.
My name is Simon, and I'm here to help you.

John: What courses do you offer?
Simon: We offer a variety of courses. Which program are you interested in?

John: How much are the fees?
Simon: Our tuition fees vary by program. Please visit our fees page for detailed information.

John: show chat history
Here’s what we’ve discussed so far:
User: What courses do you offer?
Agent: We offer a variety of courses. Which program are you interested in?
User: How much are the fees?
Agent: Our tuition fees vary by program. Please visit our fees page for detailed information.

John: bye
Simon: It was nice chatting with you, John. Goodbye!
```

## Customization
- **Agent Names:** Update the list in `generate_agent_name` to add or modify agent names.
- **Response Data:** Edit the `responses.json` file to include new patterns and responses.
- **Typing Speed:** Adjust the `time.sleep` value in `simulate_typing` to change the typing simulation speed.

## License
This project is open-source and can be used or modified freely.

