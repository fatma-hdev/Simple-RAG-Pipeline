**Simple RAG Pipeline**

A from-scratch, beginner-friendly RAG (Retrieval-Augmented Generation) pipeline in pure Python. No vector databases, no heavy frameworks — just NumPy and plain math. It comes with a simple desktop GUI so you can paste a document, ask a question, and watch every stage of the pipeline run live.

This project is built for learning. Every step (chunking, embeddings, retrieval, augmentation, generation) is implemented by hand, with the underlying equations written out right in the notebook.

### Features

- **Chunking** — splits documents into overlapping fixed-size word chunks  
- **TF-IDF Embeddings** — custom implementation (no scikit-learn) with basic English + Arabic tokenization  
- **Cosine Similarity Retrieval** — ranks and returns the top-k most relevant chunks for a query  
- **Prompt Augmentation** — builds a grounded prompt in English or Arabic  
- **Generation** — sends the final prompt to Phi-3-mini via the Hugging Face Inference API  
- **GUI** — a clean blue-themed Tkinter interface so you can run the whole pipeline interactively  

### Requirements

- Python 3.10+  
- A free [Hugging Face](https://huggingface.co/settings/tokens) account and access token  

### Setup

1. Clone the repo:
   ```bash
   git clone https://github.com/<your-username>/<your-repo>.git
   cd <your-repo>
   ```

2. Install the dependencies:
   ```bash
   python -m pip install -r requirements.txt
   ```
   On Linux you may also need:  
   `sudo apt install python3-tk`

3. Set up your Hugging Face token:
   - Copy `.env.example` to `.env`
   - Add your token: `HF_TOKEN=your_token_here`
   - Never commit the real `.env` file (it’s already in `.gitignore`)

4. Open the notebook:
   ```bash
   jupyter notebook Simple_RAG.ipynb
   ```

5. Run all cells in order (`Cell → Run All`). The last cell launches the GUI.

### How it works

```
Document → Chunking → TF-IDF Embeddings → Cosine Similarity Retrieval → Prompt Augmentation → LLM Generation → Answer
```

Each stage is explained with its equations directly in the notebook’s markdown cells.


### License

Feel free to use this project for learning. Add whatever license you prefer.
