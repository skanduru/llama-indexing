## LLAMA indexing and query

A simple tool to do indexing and query using llama

LLAMA - A 65-Billion parameter Large Language Model works by taking a sequence of words as an input and predicts a next word to recursively generate text. A simple showcase of how to do indexing and query of news information using openAI 

A StorageContext object, which provides a context for accessing the index storage. It is initialized with default settings and a specified storage directory ("./storage"). Then, the load_index_from_storage function is called, passing in the StorageContext, to load the index from the storage.

The code then creates a query_engine object by calling as_query_engine() on the loaded index. This object allows for querying the indexed news information. Several example queries are then performed using the query_engine.query() method:

a. Query 1: "What are some near-term risks to Nvidia?"
b. Query 2: "What is Microsoft working on in AI?"
c. Query 3: "Tell me about Google's new supercomputer."
d. Query 4: "Why is the price of Taiwan Semiconductor stock dropping?"

Each query is passed as an argument to query_engine.query(), which returns a response containing relevant information based on the query.

Printing the responses: The responses obtained from the query engine are printed to the console using print(response).

Note: OPENAI_API_KEY needs to be create and set as an environment variable for this code to work.

The repository was pre-populated with news from eodhistorydata.com for facilitating this

# Sample session

```bash
python index_news.py
2023-06-08 09:04:48.334845: I tensorflow/core/platform/cpu_feature_guard.cc:193] This TensorFlow binary is optimized with oneAPI Deep Neural Network Library (oneDNN) to use the following CPU instructions in performance-critical operations:  SSE4.1 SSE4.2 AVX AVX2 FMA
To enable them in other operations, rebuild TensorFlow with the appropriate compiler flags.
Token indices sequence length is longer than the specified maximum sequence length for this model (1060 > 1024). Running this sequence through the model will result in indexing errors
```

```bash
python query_news.py
2023-06-08 09:14:16.284192: I tensorflow/core/platform/cpu_feature_guard.cc:193] This TensorFlow binary is optimized with oneAPI Deep Neural Network Library (oneDNN) to use the following CPU instructions in performance-critical operations:  SSE4.1 SSE4.2 AVX AVX2 FMA
To enable them in other operations, rebuild TensorFlow with the appropriate compiler flags.
Token indices sequence length is longer than the specified maximum sequence length for this model (1344 > 1024). Running this sequence through the model will result in indexing errors

Near-term risks to Nvidia include the potential escalation of the standoff between the U.S. and China over chip exports, the potential for Japan to align with the U.S. in restricting chip exports to China, and the potential for a data center slowdown and rising inventory levels.

Microsoft is working on developing its own artificial intelligence chip that can power large language models responsible for generating human-like language. The chip is reportedly already available to a select group of employees at Microsoft and OpenAI for testing.

Google has designed a new custom chip called the Tensor Processing Unit (TPU) which is used to train its artificial intelligence models. The TPU is now in its fourth generation and is faster and more power-efficient than comparable systems from Nvidia Corp. Google has strung over 4,000 chips into a supercomputer using its custom-developed optical switches to help connect individual machines. Google has trained its largest publicly disclosed language model to date, PaLM, by splitting it across two of the 4,000-chip supercomputers over 50 days. Google has hinted at working on a new TPU that would compete with the Nvidia H100. Microsoft has also been working on ways to string together tens of thousands of Nvidia's A100 graphics chips.

The price of Taiwan Semiconductor stock may be dropping due to recent tensions between the U.S. and China, as well as the company's decision to cut its capital expenditure this year and to abandon plans to produce advanced 7-nm chips at its Kaohsiung plant. Additionally, the company's recent announcement of new chip factories in the U.S. and Japan may also be contributing to the stock's decline.
```
