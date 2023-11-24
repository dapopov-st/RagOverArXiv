# RAG Over ArXiV Papers with Finetuning

## In Progress

- RAG with LLama2 over some ArXiv papers in PDF format. Retrieving from a couple dozen ArXiv LLM papers. Currently, there is a working version with RecursiveCharacterTextSplitter (1000 chunks with 30 overlap), FAISS, and Llama2-13b. The answer quality seems to be good. I aim to increase the generation speed and see if we can add metadata to retrieval (expect retrieval over a large collection of documents to become a bottleneck).
    - Add metadata with article title for easier verification of sources.
    - Extract additional articles (for now tested with a single article and ArXiv API) and use abstract summaries to learn about articles similar/different from the ones in the vector store.  The idea is to fill in knowledge gaps in the field.
    - Tried HuggingFaceH4/zephyr-7b-beta. Much less memory (7-8GB) used and faster generation. Can be bit fragile to promping (know issue with current Zephyr models) but works well with TextLoader.

TODOS:

    - Extrapolate to multiple articles, scrape relevant websites for unknown breakthroughs 
    - Perhaps use llamaindex Knowledge Agents? 
    - Next, I aim to see if we can use Pinecone/Elasticsearch to use metadata for retrieval
    - May consider finetuning the model itself on CShorten/ML-ArXiv-Papers
