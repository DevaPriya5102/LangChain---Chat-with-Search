# LangChain - Chat with Search

## Overview

This project is a **Streamlit** web application where users can chat with an AI assistant that fetches real-time information from **Wikipedia** and **arXiv**.  
It uses **LangChain** to connect the AI model with external tools, enhancing its ability to provide accurate and updated responses.

---

## Process and Architecture

### Technologies Used
- **Streamlit**: Web app framework
- **LangChain**: Tool and agent management
- **OpenAI GPT-3.5-Turbo**: Language model
- **WikipediaAPIWrapper, ArxivAPIWrapper**: External data sources
- **dotenv**: Secure API key management

### Key Components
- **User Interface**: Built with Streamlit, including sidebar input for API key and chat interface.
- **Session State**: Manages chat history across interactions.
- **Retrieval Tools**: Wikipedia and arXiv wrappers fetch concise information.
- **Agent Setup**:
  - `initialize_agent()` combines the tools and the LLM.
  - `ZERO_SHOT_REACT_DESCRIPTION` agent type used for tool reasoning.
- **Callbacks**: `StreamlitCallbackHandler` streams live output.

### Workflow
1. User enters an OpenAI API key.
2. Chatbot welcomes the user and awaits input.
3. On query, the agent:
   - Determines whether external information is needed.
   - Searches Wikipedia/arXiv if necessary.
   - Generates and displays the response.

---

## How to Run

1. Install dependencies:
   ```bash
   pip install streamlit langchain openai python-dotenv
2. Add your API key to a .env file:
   ```ini
   OPENAI_API_KEY=your_openai_api_key
3. Start the app:
   ```bash
   streamlit run app.py
