# How to Evaluate a RAG Pipeline Using LlamaIndex and Giskard AI for a 10K Financial Report?

This project utilizes LlamaParse from LlamaIndex to parse an Amazon 10K financial report, and Giskard AI is employed to evaluate the RAG pipeline.

-> With Giskard AI, you can generate a testset to/and evaluate your RAG app.


There are two main components in the RAG evaluation Toolkit: 

## Giskard AI: Testset generation component
1- The testset generation component uses RAGET (RAG Evaluation Toolkit) to automatically generate a dataset consisting of a list of question, reference answers, and reference contexts. The last one is retrieved from your knowledge base. 

==> This component is designed to save you time from waiting to collect data from production or manually building an in-house evaluation dataset.

It uses an LLM under the hood, with specific prompt templates to instruct the model to generate various types of questions, following the LLM-as-a-judge approach.
There are 6 types of questions: simple, complex, distracting, situational, double and conversational.
Each type of question is designed to evaluate a given component of your RAG system: Generator, Retriever, ....



## Giskard AI: Evaluation component
2- The evaluation component will use the previously generated test set to assess the correctness of your RAG application. The goal is to evaluate each part of your RAG system and identify areas that need improvement.

For example, "Simple" questions will evaluate the Generator, Retriever, and Router component of your RAG app.

This component will compare the answers from your RAG app to the reference answers in the testset. 

At the end, you'll get a report that provides scores using RAGAS metrics (context recall, context precision, faithfulness, and answer relevancy), along with detailed recommendations on which components need improvement.


## Giskard AI: Clustering and Topics
-> It also clusters your KB (Knowledge Base) on different topics, and gives a score for each topic. It uses HDBSCAN to cluster the documents and uses a specific prompt (TOPIC_SUMMARIZATION_PROMPT) to extract, using an LLM, the name of the topic in the doc.


## Key Takeaways:
* You can specify the LLM you want to use for test set generation (see the Notebook example where GPT-4o-mini was used). If no model is specified, the default LLM is GPT-4, so be mindful of the associated costs.

* It's an interesting approach to use different types of questions. However, it is also valuable to generate answers based on these question types to achieve more precise responses. For example, it has been observed that some 'simple' and 'complex' questions result in the same answer. More elaborated answers for complex questions would be beneficial. In the prompt associated with "complex" questions, only the question is reformulated based on the context.

* Topics extracted from the Amazon financial report are not always relevant; for example, it would be preferable to find distinct parts like "Sales", "Liquidity and Capital Resources", or "Segments" topics.


This is an interesting framework to consider for RAG pipeline evaluation.

## About the Maintainer

This project is actively maintained by Ana Pizana, an AI & LLM Engineer with over 4 years of experience in developing and deploying intelligent systems. Ana specializes in Python, LLM technologies, and data science, with expertise in frameworks like TensorFlow and PyTorch.

For questions or collaborations, please reach out via email: aalfaropizana@gmail.com.