---
title: "TypeAgent/ts/packages/knowPro at main"
source: "https://github.com/microsoft/TypeAgent/tree/main/ts/packages/knowPro"
author:
published:
created: 2026-05-16
description: "Sample code that explores an architecture for using language models to build a personal agent that can work with application agents. - TypeAgent/ts/packages/knowPro at main · microsoft/TypeAgent"
tags:
  - "clippings"
---
## KnowPro

**KnowPro** is **experimental sample code** working towards an MVP library for [**Structured RAG**](#structured-rag-overview). KnowPro is in **active** development, with frequent updates.

The KnowPro implementation of Structured RAG is used to explore types of [**memory**](https://github.com/microsoft/TypeAgent/blob/main/ts/packages/memory/README.md).

- The TypeAgent **Dispatcher** implements **Agent Memory** using [conversation-memory](https://github.com/microsoft/TypeAgent/blob/main/ts/packages/memory/conversation/README.md) package.
- Other [memory types](https://github.com/microsoft/TypeAgent/blob/main/ts/packages/memory/conversation/README.md) include:
- The [KnowPro test app](https://github.com/microsoft/TypeAgent/blob/main/ts/examples/chat/README.md) demonstrates how to use the KnowPro API and memory implementations.

## API

- [Base interfaces and types](https://github.com/microsoft/TypeAgent/blob/main/ts/packages/knowPro/src/interfaces.ts)
- [Search](https://github.com/microsoft/TypeAgent/blob/main/ts/packages/knowPro/src/search.ts)
- [Natural language querying](https://github.com/microsoft/TypeAgent/blob/main/ts/packages/knowPro/src/searchLang.ts)
- [Answer generation](https://github.com/microsoft/TypeAgent/blob/main/ts/packages/knowPro/src/answerGenerator.ts)

### Examples

Examples of using the above APIs can be found here:

- [KnowProwTest](https://github.com/microsoft/TypeAgent/blob/main/ts/packages/knowProTest/README.md)
- [KnowPro + Memory examples](https://github.com/microsoft/TypeAgent/blob/main/ts/examples/chat/README.md)
- [Memory implementations](https://github.com/microsoft/TypeAgent/blob/main/ts/packages/memory/README.md)

## Structured RAG overview

- Structured RAG works with conversations. A conversation is a sequence of messages.
- A message can be a turn in a conversation, podcast or chat transcript. It can also be an email message, the description of an image, etc.
- Structured RAG extracts dense information from the text of messages. The extracted information includes short topic sentences, tree-structured entities, and relationship information such as actions.
- Structured information may also accompany a message. This can be timestamps, metadata such as to/from information, or the location information associated with an image. Structured information may be added to a relational table associated with the conversation as needed.
- The information associated with a message is stored in suitable indexes. These indexes allow the information to be:
	- Searched and retrieved using *query expressions* for improved precision and low latency.
		- Enumerated and filtered.
- Indexes can be updated incrementally or in the background.
- Information retrieved by executing a query can also be used to retrieve the messages it originated in.
- Natural language user requests are translated to search query expressions. These query expressions are then evaluated. Query results are used to generate answers to user requests.

You can learn more about Structured RAG in the [TypeAgent memory architecture](https://github.com/microsoft/TypeAgent/blob/main/docs/content/architecture/memory.md) document.

## KnowPro implementation

KnowPro implements the ideas of Structured RAG. KnowPro uses structured prompting and LLM to implement many core features.

KnowPro also supports:

- Natural language queries: translating natural language user requests and questions to queries.
- Answer generation: using query results from executing queries to generate natural language **answers** to user requests.

KnowPro has been primarily tested with **GPT-4o**. Results with other models are not guaranteed.

### Query flow

For each user request (including natural language):

#### Search

- Convert the user request into a query expression. Converting a natural language to query expressions can use a language model.
- For the unstructured data, the query expression consists of two parts: *scope* expressions and *tree-pattern* expressions.
- Scope expressions, such as *time range*, restrict search results to a subset of the conversation. Scope expressions can include topic descriptions, which specify the subset of the conversation that matches the description. Scope expressions can also define relationships such as actions.
- Tree-pattern expressions match specific trees extracted from the conversation and can be connected by logical operators. Tree expressions can match granular facets.
- If the user request refers to structured information, the query expression will include a relational query to be *joined* with the unstructured data query result. The relational query may include comparison operators.
- Execute the query, yielding lists of entities, topics and actions, ordered by *relevance* score.
	- The matched artifacts reference the sources from which they were derived.
- **KnowPro** uses secondary indices for matching tree expressions efficiently. It also uses secondary scope expressions such as document range and time range. KnowPro also uses secondary indices for related terms, such as "novel" for "book".

#### Generate Answers

- Select the top entities and topics returned by Search and add them to the answer prompt
- If the topics and entities do not use all of the token budget, add to the prompt the messages referenced by the top entities and topics.
- Submit the answer prompt to a language model to generate the final answer.

## Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft trademarks or logos is subject to and must follow [Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks/usage/general). Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship. Any use of third-party trademarks or logos are subject to those third-party's policies.