
Artificial Intelligence is a vast field. To understand the hierarchy of Artificial Intelligence, we can use the **Russian Doll metaphor**. In this structure, each layer is completely contained within the larger one outside it.

Here is the exact building order, from the broadest concept (the largest doll) to the most specific local implementation (the smallest doll):


1. **Artificial Intelligence (AI)** --- The Largest Doll

The macro concept. It refers to any machine or system capable of mimicking human intelligence to perform tasks --- ranging from playing chess and driving autonomous vehicles to processing natural language.

2. **Machine Learning (ML)** --- The Second Doll

A subfield entirely inside AI. Instead of a developer writing rigid, hardcoded rules (_"if X, do Y"_), computers are fed massive amounts of data and allowed to learn underlying patterns on their own.

3. **Deep Learning (DL)** --- The Third Doll

A specialized subfield inside Machine Learning. It relies on complex, deep artificial neural networks loosely inspired by the biological structures of the human brain. This breakthrough layer is where advanced language modeling was born.

4. **Large Language Models (LLMs) & Generative AI**  --- The Fourth Doll

A branch inside Deep Learning. These are massive neural networks trained on gargantuan volumes of text to understand, process, and generate human-like language. Well-known examples include OpenAI's ChatGPT, Anthropic's Claude, and Meta's Llama.

- **What is a "Model" (e.g., Qwen, Llama, Mistral):** The model is the frozen "brain" resulting from the training process. Technically, it is a single file containing billions of mathematical weights.
    
- **What do "3B", "7B", or "70B" mean:** The "**B**" stands for **Billions of parameters**. Parameters represent the virtual neural connections within the model. The rule of thumb is: more parameters make the model inherently smarter, but it requires significantly more RAM to execute.
    

5. **Engines and Runtimes (Local Infrastructure)** --- The Fifth Doll

A model file on its own (such as a `.bin` or `.gguf` file) is inert and cannot do anything by itself. The **Engine** (like **Ollama**, Llama.cpp, or vLLM) is the actual software execution layer. It loads the heavy model file into your system RAM, handles the heavy mathematical computations on your CPU or GPU, and exposes a local API server (on `http://localhost:11434`) so other tools can talk to the model.

 6. **Integrations and Editors**  --- The Smallest Doll

This is the final, innermost layer where you actually interact with the AI in your day-to-day workflow. Your text editor or IDE acts as the client that sends your code or prompt to the local engine.