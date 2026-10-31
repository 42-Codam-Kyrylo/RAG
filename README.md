# RAG
Build a Retrieval-Augmented Generation system that answers questions about codebases by retrieving relevant information and generating evidence-based responses, implementing intelligent chunking, efficient retrieval (TF-IDF/BM25)

## requirements 
- Your data models must use pydantic for validation and type safety: the structures
you exchange between stages, such as those in the Data Models section. Service or
orchestration classes (indexer, retriever, pipeline, etc.) do not have to be pydantic.

- Your system must expose a Command-Line Interface (CLI) built with Python
Fire, and progress bars (tqdm) for long-running operations.