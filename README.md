# Book-Summarization-RAG
 Summarize long documents using semantic clustering an retrieval from a vector database.


Instead of summarizing every chunk of a book, this project:

Clusters semantically similar text chunks using K-means
Selects representative chunks from each cluster
Summarizes only those key sections with GPT-3.5
Combines summaries into a final comprehensive overview with GPT-4

Result: Balanced coverage of all major themes while minimizing API costs.

Setup:
```
pip install langchain openai tiktoken pypdf scikit-learn matplotlib faiss-cpu

# Set your configuration
SOURCE_DIRECTORY = "/content/drive/MyDrive/YourBook.pdf"
openai_api_key = "your-api-key-here"
```
Key parameters

```
chunk_size=1500      # Lower = more detail, higher cost
chunk_overlap=150    # Prevents losing context at boundaries
num_clusters = 15    # 5-8: quick overview | 10-15: balanced | 20-30: detailed
llm = ChatOpenAI(model='gpt-3.5-turbo')  # Map stage (cheap)
llm4 = ChatOpenAI(model='gpt-4')         # Reduce stage (quality)
```
Supported Formats: PDF, TXT, MD, DOCX, CSV, XLS, XLSX
These are 3 of the 15 representative chunks of bullet points 
<img width="1170" height="182" alt="image" src="https://github.com/user-attachments/assets/b5a2785a-85af-498d-b55a-ea141e9e4649" />
