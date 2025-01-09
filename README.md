# Learning Gemini Chatbot

This project is a simple chatbot implementation using Google's Gemini API. It's designed as a learning tool to understand the basics of working with Large Language Models (LLMs) and building interactive chat applications.

## Educational Goals

Through this project, you'll learn about:
1. Working with AI APIs and LLMs
2. Handling asynchronous operations in JavaScript
3. Managing user input/output in terminal applications
4. Implementing error handling and graceful shutdown
5. Understanding chat session management
6. Configuration of AI model parameters

## Prerequisites

Before starting, make sure you have:
- Node.js installed (v14 or higher)
- Basic understanding of JavaScript and async/await
- A Google Cloud account and Gemini API key

## Project Setup

1. Create a new project directory:
```bash
mkdir gemini-chatbot
cd gemini-chatbot
```

2. Initialize a new Node.js project:
```bash
npm init -y
```

3. Install required dependencies:
```bash
npm install @google/generative-ai dotenv
```

4. Create a `.env` file in the root directory:
```
GEMINI_API_KEY=your_api_key_here
```

## Code Structure Explained

### 1. API Initialization
```javascript
const genAI = new GoogleGenerativeAI(process.env.GEMINI_API_KEY);
```
This line initializes the Gemini API client. We use environment variables to keep the API key secure.

### 2. Chat Configuration
The `initializeChat` function sets up important parameters:

- **History**: Initial context for the chat
- **Generation Config**:
  - `maxOutputTokens`: Controls response length
  - `temperature`: Affects creativity (higher = more creative)
  - `topP`: Controls diversity of responses
  - `topK`: Affects focus of responses

### 3. Chat Loop Implementation
The chat loop uses a recursive pattern to:
1. Get user input
2. Send it to Gemini
3. Display the response
4. Repeat

This pattern allows for continuous conversation while handling asynchronous operations properly.

## Key Learning Concepts

### Async/Await Pattern
```javascript
async function chatLoop() {
  const response = await chat.sendMessage(input);
}
```
The code uses async/await to handle asynchronous API calls in a clean, readable way.

### Error Handling
The implementation includes multiple layers of error handling:
1. Try/catch blocks for API calls
2. Global error handler for uncaught exceptions
3. Graceful shutdown procedures

### User Input Management
The readline interface demonstrates how to:
- Create an interactive command-line interface
- Handle user input continuously
- Implement exit commands
- Maintain a conversation flow

## Customization Opportunities

1. Model Parameters
```javascript
generationConfig: {
  temperature: 0.7,  // Experiment with different values
  topP: 0.8,        // Try adjusting these parameters
  topK: 40
}
```
Try adjusting these values to see how they affect the bot's responses.

2. Chat History
You can modify the initial chat history to give your bot different personalities or capabilities.

3. Response Processing
Add functions to process or format the bot's responses in different ways.

## Learning Exercises

1. **Parameter Experimentation**
   - Try different temperature values (0.1 to 1.0)
   - Observe how responses change
   - Document the differences

2. **Error Handling**
   - Intentionally cause errors (e.g., invalid API key)
   - Observe how the error handling works
   - Try implementing additional error cases

3. **Feature Addition**
   - Add command history
   - Implement response formatting
   - Add conversation saving/loading

## Common Issues and Solutions

1. **API Key Issues**
   - Make sure the `.env` file is properly configured
   - Check if the API key has proper permissions

2. **Response Timeout**
   - Implement timeout handling
   - Add retry logic for failed requests

3. **Memory Usage**
   - Monitor chat history size
   - Implement cleanup for long conversations

## Next Steps

After mastering this basic implementation, consider:
1. Adding a web interface
2. Implementing conversation memory
3. Adding specific commands or skills
4. Integrating with other APIs
5. Adding message streaming
6. Implementing chat history persistence

## Resources for Further Learning

1. [Gemini API Documentation](https://ai.google.dev/docs)
2. [Node.js Async Programming Guide](https://nodejs.org/en/learn/asynchronous-work)
3. [Error Handling Best Practices](https://nodejs.org/en/learn/error-handling)

## Support

If you encounter any issues or have questions while learning:
1. Check the error message carefully
2. Review the relevant documentation
3. Try debugging with console.log statements
4. Search for similar issues online

Remember, the goal is to learn - don't be afraid to experiment and make mistakes!
