---
date: 2025-05-05
---
People are using AI locally to capture their emails, index their files and build knowledge around them. Such a system could help with personal tasks for example to create a grocery list from emails, collecting follow-up actions, learning from email writing style and enhancing on it, and finally building a semantic index of all raw sources of information.
People open-sourced ([[matvellosoknowledge]]) an implementation of this on Github that connects to email apps and uses and LLM to create indexes. However this project uses embeddings and cosine-similarity for retrieving data and is essentially RAG-based again. This is important since it make the dependency uninterpretable compared to a graph structure.
Such a system can be used to process (index) private information locally then people can merge their local knowledge base with a more bigger common knowledge base, similar to how software developers open pull request to a code base.
