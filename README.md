# 🔷 Simple RAG Pipeline

A from-scratch, beginner-friendly implementation of a **Retrieval-Augmented Generation (RAG)** pipeline in Python — no vector databases or heavy frameworks, just NumPy and plain math. Includes a desktop GUI (Tkinter) so you can paste a document, ask a question, and watch each pipeline stage run live.

Built for learning: every step (chunking, embeddings, retrieval, augmentation, generation) is implemented manually with the underlying equations documented inline in the notebook.

## ✨ Features

- **Chunking** — splits documents into overlapping fixed-size word chunks
- **TF-IDF Embeddings** — custom implementation (no scikit-learn) with basic English + Arabic tokenization
- **Cosine Similarity Retrieval** — ranks and returns the top-k most relevant chunks for a query
- **Prompt Augmentation** — builds a grounded prompt in English or Arabic
- **Generation** — sends the final prompt to a language model (Phi-3-mini) via the Hugging Face Inference API
- **GUI** — a simple blue-themed Tkinter interface to run the whole pipeline interactively

## 🖥️ Requirements

- Python 3.10+
- A free [Hugging Face](https://huggingface.co/settings/tokens) account and access token

## ⚙️ Setup

1. Clone the repo:
   ```bash
   git clone https://github.com/<your-username>/<your-repo>.git
   cd <your-repo>
   ```

2. Install dependencies:
   ```bash
   python -m pip install -r requirements.txt
   ```
   > On Linux, Tkinter may need a separate system package: `sudo apt install python3-tk`

3. Set up your Hugging Face token:
   - Copy `.env.example` to `.env`
   - Add your token: `HF_TOKEN=your_token_here`
   - **Never commit your real `.env` file** — it's already excluded via `.gitignore`

4. Open the notebook:
   ```bash
   jupyter notebook Simple_RAG.ipynb
   ```

5. Run all cells in order (`Cell → Run All`). The last cell opens the GUI window.

## 🖼️ How it works

```
Document → Chunking → TF-IDF Embeddings → Cosine Similarity Retrieval → Prompt Augmentation → LLM Generation → Answer
```

Each stage is documented with its equations directly inside the notebook's markdown cells.

## ⚠️ Security note

This project reads your Hugging Face token from an **environment variable** (`HF_TOKEN`), not hardcoded in the source — always keep API tokens out of code that goes on GitHub.

## 📄 License

Feel free to use this project for learning purposes. Add a license of your choice (e.g. MIT) if you plan to share it publicly.
