# Arch9-2024-frankspiess

Use cases and how to implement the solutions:

* Summary of a meeting recording
  * Business problem: you have meeting recordings, but it is a lot of effort to transcribe and extract the key discussion points.
  * Solution: a fully automated pipeline to do both document hosting, transcription and key topics extraction using AWS services and any of the LLMs provided by Amazon Bedrock.
  * How to deploy on AWS: https://aws.amazon.com/blogs/machine-learning/summarize-call-transcriptions-securely-with-amazon-transcribe-and-amazon-bedrock-guardrails/

* Customer Support Chatbot with Retrieval Augmented Generation (add private documents to your LLM retrieval)
  * Business problem: you have internal, company specific private data which should be part of the search space that your Chatbot can cover - to answer questions.
  * Solution: this time, a fully open sourced approach consisting of Ollama as a platform, Llama3 as LLM, and ChromaDB as vector datastore.
  * How to deploy using Ollama: https://www.youtube.com/watch?v=FQTCLOUnIzI by Matt Williams
  * Compute Layer used: EC2 instance type "g4dn.xlarge" https://instances.vantage.sh/aws/ec2/g4dn.xlarge

* Offline image analysis
  * Business problem:
  * Solution:
  * How to deploy:

* Clinical decision support
  * Business problem:
  * Solution:
  * How to deploy:

Further reading, more advanced topics:
* Run any GGUF model from Huggingface in Ollama: https://www.youtube.com/watch?v=LQJVz-B_mZI by Matt Williams
