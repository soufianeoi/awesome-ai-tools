# Vector Databases

## Chroma

[![GitHub](https://img.shields.io/github/stars/chroma-core/chroma?style=flat-square)](https://github.com/chroma-core/chroma)

**Type:** Embedded, serverless

**Description:** Open-source, AI-native vector database. Runs in-process or as a server.

```python
import chromadb
client = chromadb.Client()
col = client.create_collection("docs")
col.add(documents=["Hello world"], ids=["1"])
results = col.query(query_texts=["Hello"], n_results=1)
print(results)
```

## Qdrant

[![GitHub](https://img.shields.io/github/stars/qdrant/qdrant?style=flat-square)](https://github.com/qdrant/qdrant)

**Type:** Server (Docker), cloud

**Description:** High-performance vector search with filtering, written in Rust.

```python
from qdrant_client import QdrantClient
client = QdrantClient(":memory:")
client.create_collection("docs", vectors_config={"size": 384, "distance": "Cosine"})
```

## LanceDB

[![GitHub](https://img.shields.io/github/stars/lancedb/lancedb?style=flat-square)](https://github.com/lancedb/lancedb)

**Type:** Embedded, serverless

**Description:** Serverless vector database built on Lance columnar format. No server needed.

```javascript
const lancedb = require('vectordb');
const db = await lancedb.connect('data.db');
const table = await db.createTable('vectors', [{ vector: [0.1, 0.2], text: 'hello' }]);
```

## Weaviate

[![GitHub](https://img.shields.io/github/stars/weaviate/weaviate?style=flat-square)](https://github.com/weaviate/weaviate)

**Type:** Server (Docker), cloud

**Description:** Vector search with built-in LLM integration, hybrid search (vector + keyword).

```python
import weaviate
client = weaviate.connect_to_local()
collection = client.collections.get("Document")
```

## Pinecone

[![Website](https://img.shields.io/badge/Pinecone-764ABC?style=flat-square)](https://pinecone.io)

**Type:** Cloud (managed)

**Description:** Fully managed vector database with free tier (1 pod, 100k vectors).

```python
from pinecone import Pinecone
pc = Pinecone(api_key=PINECONE_API_KEY)
index = pc.Index("my-index")
index.upsert(vectors=[{"id": "1", "values": [0.1, 0.2]}])
```

## Milvus

[![GitHub](https://img.shields.io/github/stars/milvus-io/milvus?style=flat-square)](https://github.com/milvus-io/milvus)

**Type:** Server (Docker), cloud (Zilliz)

**Description:** Scalable vector database for billion-scale similarity search.

```python
from pymilvus import connections, Collection
connections.connect(host='localhost', port='19530')
collection = Collection("docs")
```
