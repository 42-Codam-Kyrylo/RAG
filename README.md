# RAG
Build a Retrieval-Augmented Generation system that answers questions about codebases by retrieving relevant information and generating evidence-based responses, implementing intelligent chunking, efficient retrieval (TF-IDF/BM25)

## requirements 
- Your data models must use pydantic for validation and type safety: the structures
you exchange between stages, such as those in the Data Models section. Service or
orchestration classes (indexer, retriever, pipeline, etc.) do not have to be pydantic.

- Your system must expose a Command-Line Interface (CLI) built with Python
Fire, and progress bars (tqdm) for long-running operations.

## 	vVI.1 Indexing the codebase

Chunk size is configurable through a CLI argument (--max_chunk_size),
with a default of 2000 characters. Do not go above it: the
moulinette rejects any retrieved source longer than 2000 characters
(its max_context_length), and a single over-long source makes your
whole output invalid. Smaller chunks are fine; report the effect on
your recall@k.

## VI.2 Retrieval

file_path must match the corpus path exactly (e.g.
data/raw/vllm-0.10.1/docs/features/lora.md). The grader compares
paths verbatim, so a path with a different prefix never matches.