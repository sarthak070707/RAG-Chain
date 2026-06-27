# RAG-Chain

A Retrieval-Augmented Generation (RAG) system that answers natural-language
questions over your own documents. Upload PDFs, and the app retrieves the most
relevant passages via embeddings and generates grounded, source-backed answers
instead of hallucinating.

> **Note:** Built on an open-source RAG base and reworked for my own use case —
> _[REPLACE THIS LINE with what you actually changed: e.g. swapped the embedding
> model, reworked chunking/retrieval, redid the UI, changed the document handling,
> added feature X, etc.]_

## What it does

- **Natural-language Q&A** over a custom document set, with concise, grounded answers.
- **Bring your own documents** — upload PDFs to expand the knowledge base.
- **Similarity search** over AI embeddings to pull the most relevant context per query.
- **Simple web interface** for querying and uploading.

## How it works

```
PDF upload  ->  chunk text  ->  embeddings  ->  vector store (ChromaDB)
                                                      |
User query  ->  embed query ->  similarity search -> top-k context -> LLM -> grounded answer
```

Retrieval grounds every answer in the uploaded documents, which keeps responses
factual and reduces hallucination compared to asking the LLM directly.

## Tech stack

- **Language:** Python 3.10+
- **Framework:** LangChain
- **Vector store:** ChromaDB
- **Embeddings:** Google Gemini API (embedding-001)
- **LLM:** Google Gemini API (gemini-1.5-pro)
- **PDF parsing:** PyPDFLoader
- **Chunking:** SentenceTransformersTokenTextSplitter
- **UI:** Streamlit

## Run locally

```bash
pip install -r requirements.txt
streamlit run app.py
```

1. Add your Google API key in the sidebar.
2. (Optional) Upload PDFs to build the knowledge base.
3. Ask questions in the main interface.

## Notes

This is a learning / portfolio project. Answer quality depends on the coverage
and quality of the uploaded documents.

## Author

**Sarthak Arya** · [github.com/sarthak070707](https://github.com/sarthak070707) · sarthakarya4@gmail.com
