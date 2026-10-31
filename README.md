# Backrooms RAG

An educational Retrieval-Augmented Generation (RAG) chatbot project centered on [Backrooms Level 37 — Sublimity](https://backrooms-wiki.wikidot.com/level-37). The project prioritizes a small, readable, and reproducible workflow for a university assignment.

## Planned modes

- **Wiki QA:** Answer questions using information retrieved from the Level 37 Wiki source material.
- **Text Adventure:** A minimal exploration experience in which an LLM narrates the consequences of player actions.

Both modes will use the same RAG knowledge base. The initial text adventure will rely only on conversation history; it will not include combat, inventory, maps, dice, or a complex game-state system.

## Notebooks

- **RAG01.ipynb** will load reviewed chunks, generate multilingual embeddings, build a FAISS vector index, and export `rag-data.zip`.
- **RAG02.ipynb** will download `rag-data.zip`, retrieve relevant documents, use Groq for responses, and provide a Gradio interface for both planned modes.

## Project structure

```text
backrooms-rag/
├── data/
│   ├── level37_raw.txt      # Original Wiki text placeholder
│   └── chunks.json          # Reviewed semantic chunks placeholder
├── RAG01.ipynb              # Vector database workflow
├── RAG02.ipynb              # Chatbot workflow
├── README.md
└── .gitignore
```

## Planned development phases

1. Repository structure and documentation.
2. Collect Level 37 source text and prepare semantic chunks with metadata.
3. Implement RAG01 and export the FAISS database as `rag-data.zip`.
4. Implement RAG02 with retrieval and Groq-based QA.
5. Add Gradio and a minimal text adventure mode.
6. Test in a clean Google Colab environment and prepare assignment documentation.

This project is an educational assignment. Features described above are planned and are not implemented in this initialization phase.
