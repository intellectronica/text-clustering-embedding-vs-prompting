# Text Clustering: Embedding vs Prompting

Embeddings are a foundational building block of LLMs - by locating semantics in a multi-dimensional space they allow LLMs to make sense of meaning and "understand" what texts are about. In this sample, we look at two ways of using embeddings for the purpose of clustering texts by their meaning. In the first, we use the embeddings directly and learn the clusters based on their embedding vectors. In the second, with summarise the texts and pass them on to a powerful LLM, prompting it to cluster the articles. As we'll see, both approaches work well, and each approach has its advantages.

Learning clusters directly from embeddings:
- Fast and inexpensive
- Requires an understanding of basic machine learning methods (K-Means clustering)
- Does not provide any additional information about the clusters, since the simple machine learning algorithm we're using is working directly with the numerical representation of the embeddings and does not have any insight into their meaning.

Prompting an LLM to cluster the articles:
- Relatively slow and expensive - this is a task for GPT-4, simpler LLMs do not achieve it with convincing results
- Easy to accomplish - we're "programming" the LLM in English, no additional knowledge of machine-learning techniques required
- Can provides additional information about the clusters, since the clustering is happening within the context of the LLM, where the summary of the articles is available

In conclusion, we can achieve pretty good clustering using both techniques. Using LLMs to summarise the articles and then asking for a clustering gets us excellent results, but at a price - we need one minute and a half to complete the task, and the costs for making the LLM calls add up. Learning the clustering from the embeddings directly is very fast (4 seconds) and inexpensive, but getting high quality results is much harder, and we don't get the added benefit of the LLM being able to reason about the clusters and give them a clear description, we have to do that using a human, and that's many times more expensive.

See [notebook](text-clustering-embedding-vs-prompting.ipynb).
