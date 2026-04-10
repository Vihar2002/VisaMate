# VisaMate - AI-Powered Visa Advisory Chatbot

An intelligent visa advisory chatbot built with the OpenAI Assistants API that answers visa-related questions for Ireland, the UK, and the Schengen Area. VisaMate grounds every response in a curated knowledge base of official visa documentation, ensuring accurate and reliable guidance for students and tourists.

## What It Does

VisaMate acts as a virtual visa advisor. You ask it questions like:

- "What documents do I need for an Irish student visa?"
- "How much bank balance is required for a Schengen tourist visa?"
- "Can I work part-time on a UK student visa?"

It retrieves the relevant information from its knowledge base and gives you a clear, grounded answer. When date or currency calculations are involved (e.g., visa validity windows, fee conversions), it uses a built-in code interpreter to compute them on the fly.

## How It Works

VisaMate is built on four core components:

1. **Vector Store (Knowledge Base):** Six curated text files covering student and tourist visa requirements for Ireland, the UK, and the Schengen Area are uploaded to an OpenAI vector store. These documents are sourced from official immigration authorities and consolidated into a structured, searchable format.

2. **File Search (RAG):** When you ask a question, the assistant uses file search to retrieve the most relevant passages from the vector store. This ensures every answer is grounded in real documentation rather than general model knowledge.

3. **Code Interpreter:** For questions involving calculations (dates, fees, currency conversions), the assistant spins up a code interpreter to compute accurate results rather than guessing.

4. **Multi-Turn Conversation Threading:** Each chat session maintains a persistent thread, so the assistant remembers context from earlier in the conversation. You can ask follow-up questions naturally without repeating yourself.

## Tech Stack

- **Language:** Python
- **AI:** OpenAI Assistants API (GPT-3.5 Turbo)
- **Tools:** File Search (vector store retrieval), Code Interpreter
- **Knowledge Base:** 6 curated visa reference documents (TXT)

## Project Structure

```
VisaMate/
|-- ViharDilip_Yeole_GENAIProject_Code.ipynb   # Main notebook
|-- Ireland_Student_Visa_Info.txt               # Ireland student visa docs
|-- Ireland_Tourist_Visa_Info.txt               # Ireland tourist visa docs
|-- UK_Student_Visa_Info.txt                    # UK student visa docs
|-- UK_Tourist_Visa_Info.txt                    # UK tourist visa docs
|-- Schengen_Student_Visa_Info.txt              # Schengen student visa docs
|-- Schengen_Tourist_Visa_Info.txt              # Schengen tourist visa docs
|-- README.md
```

## Setup & Usage

### Prerequisites

- Python 3.8+
- An OpenAI API key with access to the Assistants API

### Installation

```bash
pip install openai
```

### Running the Chatbot

1. Clone this repository:
   ```bash
   git clone https://github.com/Vihar2002/VisaMate.git
   cd VisaMate
   ```

2. Open the Jupyter notebook:
   ```bash
   jupyter notebook ViharDilip_Yeole_GENAIProject_Code.ipynb
   ```

3. Add your OpenAI API key in the first cell:
   ```python
   client = OpenAI(api_key="your-api-key-here")
   ```

4. Run all cells sequentially. The notebook will:
   - Create a vector store and upload the 6 knowledge base files
   - Wait for indexing to complete
   - Build the VisaMate assistant with file search and code interpreter tools
   - Launch an interactive chat loop in the notebook

5. Start asking questions:
   ```
   You: What documents do I need for an Irish student visa?
   VisaMate: To apply for an Irish student visa (Long-Stay "D" Visa), you need...
   ```

6. Type `exit` or `quit` to end the session.

## Key Features

- **Grounded Answers:** Every response is backed by retrieved passages from official visa documentation, not general AI knowledge.
- **Multi-Region Coverage:** Covers Ireland, UK, and Schengen Area for both student and tourist visa categories.
- **Computation Support:** Uses code interpreter for date calculations, fee estimates, and currency-related queries.
- **Conversational Memory:** Maintains context across multiple turns within a session, so follow-up questions work naturally.
- **Rate Limit Handling:** Built-in retry logic with backoff for API rate limits, ensuring the chatbot stays responsive.

## Knowledge Base Sources

The knowledge base documents are consolidated from official sources including:

- Irish Naturalisation and Immigration Service (INIS)
- Department of Justice, Ireland
- UK Visas and Immigration (UKVI)
- EU Schengen Visa Info

All documents were structured and formatted for optimal retrieval performance.

## Built With

This project was built as part of the Generative AI module at University College Dublin (MSc Computer Science, 2024-2025).

## Author

**Vihar Dilip Yeole**
- LinkedIn: [linkedin.com/in/viharyeole](https://www.linkedin.com/in/viharyeole/)
- GitHub: [github.com/Vihar2002](https://github.com/Vihar2002)
- Email: viharyeole@gmail.com
