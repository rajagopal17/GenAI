
# Generative AI with RAG application
***Llama-index advanced retrievers with opensource llm (mistral):***

***Business case:***  Organizations have large amounts of proprietary data in shared drives. Timely access of such data in a organized way is usually a challenge
and takes lot of time and resources.  If we can build a application which can answer the queries and point to the right documents it will really help to save time and efforts
of employees.

**Platform used**: RAG (Retreival augmented generation) apllication provided by llama-index platform provided very efficient tools for search and query huge amounts of data
               Also i have used open source llm -Mistral provided by togetherAPI


Key Features of LLMIndex for RAG Applications

* **Fast Text Indexing**: LLMIndex offers faster text indexing compared to traditional methods, allowing users to process 
massive volumes of data quickly in the context of RAG applications.
* **Flexible Data Types**: It supports various data types, including character vectors, data frames, and corpus objects, 
making it a versatile choice for RAG applications.
* **Advanced Search Capabilities**: LLMIndex enables users to perform complex searches based on multiple keywords or 
phrases, Boolean operators, proximity terms, and more, ensuring accurate and relevant results.

**Project:** Implementing LLMIndex in a RAG Application
In this project, we have indexed SAP documentation (multiple pdf files) . By indexing the documents we can efficiently search for various sub-modules, technical names,
configuration steps and other details without having to read the entire document. We can query the database with simple questions in natural language and get the answers.


***Conclusion:***
LlamaIndex serves as a powerful tool in the arsenal of RAG applications by providing advanced text mining 
capabilities that enable fast and accurate processing of vast amounts of unstructured data. Its flexibility and advanced 
search functionalities make it an indispensable asset for organizations looking to improve their risk assessment, grading,
and overall decision-making processes.

# RAG with OpenAI Assistant
#In this demo, the usage of OpenAI assistants functionality is provided.


*   data is stored in openai's vector database and queried from it (similiar to llamaindex)
*   we can create required number of assitants based on the required topic (each assistant queries its own vectorstore)


*   each assistant need to be created as a function with detailed function name using gpt-3.5/ gpt-4o
*   then create a tool list with  the assistants (function names)


*   using anthropic tool calling, required functions can be executed automatically
*   this is similiar to function calling discussed in another notebook, the only difference being, functions are created using openai assistants

#Points to check:


*   need to check how the token usage for retrieving data using gpt-3.5-turbo model from the vectorstore (cannot retrieve data using non-openai model)
*   also not sure where the vectorstore is stored in openai and will there be any privacy concerns


*   also we do not have any control on the vectorstore
*   if this is not cost effective we can use llamaindex with latest embeddings from openai/cohere/voyager/Ragatouille, create our own vectorstore and retrieve it using openai/claude models by creating a function wrapper on the retriever
