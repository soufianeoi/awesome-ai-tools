# Data & ETL

## Unstructured

[![GitHub](https://img.shields.io/github/stars/Unstructured-IO/unstructured?style=flat-square)](https://github.com/Unstructured-IO/unstructured)

**Description:** Document parsing for RAG — extract text from PDFs, HTML, Word, PowerPoint, images.

```python
from unstructured.partition.auto import partition
elements = partition("document.pdf")
for el in elements:
    print(el.text)
```

## txtai

[![GitHub](https://img.shields.io/github/stars/neuml/txtai?style=flat-square)](https://github.com/neuml/txtai)

**Description:** AI-powered data pipeline — embeddings, search, RAG, extraction, all in one.

```python
import txtai
app = txtai.Embeddings()
app.index(["Hello world", "Goodbye world"])
print(app.search("hello"))
```

## Docling

[![GitHub](https://img.shields.io/github/stars/DS4SD/docling?style=flat-square)](https://github.com/DS4SD/docling)

**Description:** IBM's document understanding — PDF to Markdown/JSON with layout preservation.

```python
from docling.document_converter import DocumentConverter
conv = DocumentConverter()
result = conv.convert("document.pdf")
print(result.document.export_to_markdown())
```

## LangChain Document Loaders

[![GitHub](https://img.shields.io/github/stars/langchain-ai/langchain?style=flat-square)](https://github.com/langchain-ai/langchain)

**Description:** 100+ document loaders — PDF, HTML, CSV, Notion, Confluence, GitHub, Slack, YouTube.

```python
from langchain_community.document_loaders import PDFLoader
loader = PDFLoader("doc.pdf")
docs = loader.load()
```

## LlamaParse

[![Website](https://img.shields.io/badge/LlamaParse-A463FF?style=flat-square)](https://llamacloud.com)

**Description:** LlamaIndex's document parsing service. Free tier: 1000 pages/day.

```python
from llama_parse import LlamaParse
parser = LlamaParse(result_type="markdown")
docs = parser.load_data("document.pdf")
```

## Semantic Chunking (Chunking Strategies)

Break text into semantically meaningful chunks instead of fixed-size windows. This is a technique rather than a library, but crucial for RAG quality.

```python
# Simple semantic chunking
def semantic_chunk(text, max_chars=512):
    chunks = []
    for paragraph in text.split('\n\n'):
        if len(paragraph) <= max_chars:
            chunks.append(paragraph)
        else:
            chunks.extend(paragraph.split('. '))
    return chunks
```
