# Backrooms RAG

An educational Retrieval-Augmented Generation (RAG) chatbot project centered on [Backrooms Level 37 — Sublimity](https://backrooms-wiki.wikidot.com/level-37). The project prioritizes a small, readable, and reproducible workflow for a university assignment.

## Planned modes

- **Wiki QA:** Answer questions using information retrieved from the Level 37 Wiki source material.
- **Text Adventure:** A minimal exploration experience in which an LLM narrates the consequences of player actions.

Both modes will use the same RAG knowledge base. The initial text adventure will rely only on conversation history; it will not include combat, inventory, maps, dice, or a complex game-state system.

## Notebooks

- **RAG01.ipynb** loads reviewed chunks, generates multilingual embeddings, builds a FAISS vector index, and exports `rag-data.zip`.
- **RAG02.ipynb** downloads `rag-data.zip`, retrieves relevant documents, and uses Groq for grounded Wiki QA. Gradio and Text Adventure are reserved for a later phase.

## Run RAG02 in Google Colab

1. Open `RAG02.ipynb` in Colab and add `GROQ_API_KEY` to Colab Secrets. Outside Colab, set the same environment variable.
2. Run the notebook from top to bottom. It installs `sentence-transformers`, `faiss-cpu`, `groq`, and `requests`, then downloads the public `rag-data.zip` from this repository's `main` branch.
3. Review the six QA examples or enter a custom question. Set `DEBUG_RETRIEVAL = True` to inspect retrieval scores separately from the answer.

The Groq SDK model ID is `openai/gpt-oss-120b`. The notebook reads the embedding model and normalization settings from the ZIP's `config.json`; it does not rebuild the FAISS database. The ZIP contains `rag_database/index.faiss`, `rag_database/chunks.json`, and `rag_database/config.json`.

## Project structure

```text
backrooms-rag/
├── data/
│   ├── level37_raw.txt      # Original Wiki text placeholder
│   └── chunks.json          # Reviewed semantic chunks placeholder
├── RAG01.ipynb              # Vector database workflow
├── RAG02.ipynb              # Groq Wiki QA workflow
├── rag-data.zip             # Exported FAISS database
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

This project is an educational assignment. The retrieval and Groq QA notebook is implemented; the interface and game mode remain planned.

## Source attribution

The Phase 1 dataset reproduces material from [Level 37 - "Sublimity"](https://backrooms-wiki.wikidot.com/level-37) by egglord, from the Backrooms Wiki. Source URL: `https://backrooms-wiki.wikidot.com/level-37`. The page is licensed under [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/).
