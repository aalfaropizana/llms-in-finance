# How to Boost your RAG Pipeline Using Query Transformation, Hypothetical Answering for Better Re-ranking and Performance?

"What impact did the global outage of CrowdStrike, extensively used by Microsoft, have on Microsoft's stock price?"

## Steps: 
* To tackle this, I will employ the hypothetical answer re-ranking technique, comparing 3 LLMs (gpt-4o-mini, gpt-4o, gpt-3.5-turbo):

  * Goal: I will evaluate whether the hypothetical answer can improve the re-ranking and the retrieved context, and subsequently enhance the LLM's response within our RAG pipeline. Alternatively, we will assess if the original query alone is sufficient to retrieve the appropriate context and deliver accurate results.

  - Different techniques will be employed: Query Transformation, Hypothetical Answers, Embeddings, and Similarity Scoring to retrieve the relevant context from news articles fetched from the NEWS API.

  - In these techniques, we will compare the capabilities of three LLMs: gpt-4o-mini (the latest small model from OpenAI), gpt-4o (the most capable LLM from OpenAI), and gpt-3.5-turbo."

  - I will use use 3 evaluation metrics from deepEval for RAG pipelines: Faithfulness, Context Relevancy and Answer relevancy.
  These metrics are explained in the notebook. 
  If you haven't heard of DeepEval yet, check out the Confident AI website, documentation, and repository. It's a very interesting evaluation library.

  - We will compare the three LLMs using two techniques: Hypothetical Answer Re-ranking vs. Original Query Retrieval.


## Key Takeaways:

- Notably, gpt-4o-mini shows the best score among the other LLMs, in both hypothetical technique and original query based technique. Its score in answer relevancy was significantly better than GPT-4o (0.85 vs. 0.5 in hypothetical technique) and even better than GPT-3.5-turbo (0.3). Furthermore, its score in faithfulness was better than the others.

- The average score, across the three metrics, for the results retrieved using the hypothetical answer is better than those based on the original query when using GPT-4o-mini. This higlights the fact that the re-ranking process leads to better results.

- The retrieved context needs to be re-worked... (more details at the end of the notebook)

## About the Maintainer

This project is currently maintained by Ana Pizana, an AI & LLM Engineer with 4+ years of professional experience. Ana specializes in Python, PostgreSQL, Rust, JAVA, NumPy, Pandas, MatLab, TensorFlow, Scikit-learn, NLTK, and PyTorch.

*   **Email:** aalfaropizana@gmail.com
*   **LinkedIn:** [Your LinkedIn Profile] (Please update with your actual LinkedIn URL)
*   **GitHub:** [Your GitHub Profile] (Please update with your actual GitHub URL)