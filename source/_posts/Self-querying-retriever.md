---
title: How to Build a RAG System with a Self-Querying Retriever in LangChain
date: 2024-06-07
#type:
#updated:
#comments:
#description:
#keywords:
cover: https://miro.medium.com/v2/resize:fit:4800/format:webp/1*nvFDvcE7P-Wgr0ZFRE3mnQ.png
tags: 
    - NLP
    - RAG
    - LangChain
#mathjax:
#katex:
#aside:
#aplayer:
#highlight_shrink:
---

Original post: [click here](https://towardsdatascience.com/how-to-build-a-rag-system-with-a-self-querying-retriever-in-langchain-16b4fa23e9ad)  

### Idea
Why can't I use natural language to query a movie based more on the vibe or the substance of a movie, rather than just a title or actor?  

> e.g. search: I liked "Everything Everywhere all at Once", give me a similar film, but darker.  

### Action: Build Film Search
RAG-based system, takes a user's query, embeds it, and does a similarity search to find similar films.  
Different to vanilla RAG: using self-querying retriever.  

Ability: allow filtering movies by their metadata, before doing a similarity search. 

> e.g. query: "Recommend horror movies made after 1980 that features lots of explosions" 

The search will first filter out all films that are not "horror movies made after 1980", before doing a similarity search for films that "feature lots of explosions".

### Retrieve the Data

Data: The Movie Database (TMDB)  
pulled film attributes from their API.  
upload documents to Pinecone.
convert each CSV file to a LangChain document, then specify which fields should be the <u>primary content</u> and which fields should be the <u>metadata</u>.  

```DirectoryLoader``` from LangChain  
takes care of loading all csv files into documents.  
specify:
> 1. page-content: (overview + keywords) will be emebeded and used in similarity search during the retrieval phase.  
> 2. metadata: solely for filtering purposes before similarity search is done.

```SQLRecordManager``` ensures that duplicate documents are NOT uploaded to Pinecone.  
Embedding model: ```text-embedding-ada-002``` OpenAI

### Creating the self-querying retriever
allow to filter the movies that retrieved during RAG via metadata.  
1. choose vector store, make sure it supports filtering by metadata.  
2. what types of comparators are allowed for each vector store.
    > e.g. comparator "eq", eq('Genre', 'SciFi')
3. Few-shot learning, feed the model examples of user queries and corresponding filters. LMs can use their "reasoning" abilities and world knowledge to generalize from these few-shot examples to other user queries.
4. model has to know a description of each metadata fields.

### Creating the chat model
build self-querying retriever -> build standard RAG model  

Define chat model (summary model):
takes in a context (retrieved films + system message)  
respond with a summary of each recommendation  
keep low cost: ```GPT-3.5 Turbo```, keep best result: ```GPT-4 Turbo```

Issue:  
presented with no film data in its context, the model would use its own(faulty) memory to try and recommend some films. <span style="color:red">Not good.</span>

### Limitations of this film search
No saving recommendation histories.  
Need to update raw data weekly.  
Bad metadata filtering by the self-querying retrieval.
> e.g. "Ben A. films" could mean "Ben A. is the star" or "Ben A. directed"  
> Clarification of the query would be helpful

Possible improvements:  
Re-ranking of documents after retrieval.  
Have a chat model that you can converse with in multi-turn conversations rather than just a QA bot.