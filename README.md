# LangGraph Basic Chatbot with Google Gemini

A lightweight conversational workflow built using **LangGraph** and **LangChain** with the Google Gemini API. This project demonstrates how to structure a single-node state graph to process user input and return model responses.

---

## Architecture Overview

The application implements a directed acyclic graph (DAG) using `StateGraph`:

1. **State**: Manages the dictionary carrying the user `message` and the model `response`.
2. **`START` Node**: Routes the initial input into the chatbot node.
3. **`chatbot` Node**: Queries the Gemini model with `state["message"]` and updates `state["response"]`.
4. **`END` Node**: Concludes the graph execution and outputs the final state.