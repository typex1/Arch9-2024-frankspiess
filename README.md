# Arch9 2024: "Right-sizing AI: The Case of Small Language Models" by Frank Spiess

**Outline:**
As Large Language Models (LLMs) continue to dominate the AI landscape, their limitations—such as high resource consumption, significant environmental impact, and challenges in task-specific fine-tuning—are becoming increasingly evident. In contrast, Small Language Models (SLMs) offer a more lightweight, efficient, and adaptable alternative. This talk will delve into the rise of SLMs, their capacity to address key issues associated with LLMs, and recent innovations like model merging and fine-tuning. Through real-world examples, we will explore how SLMs are influencing the future of AI and why they might be the ideal choice for your next project.

**Use cases and how to implement the solutions:**

* **Use case 1**: "Summary of a meeting recording"
  * Business problem: you have meeting recordings, but it is a lot of effort to transcribe and extract the key discussion points.
  * Solution: a fully automated pipeline to do both document hosting, transcription and key topics extraction using AWS services and any of the LLMs provided by Amazon Bedrock.
  * How to deploy on AWS: https://aws.amazon.com/blogs/machine-learning/summarize-call-transcriptions-securely-with-amazon-transcribe-and-amazon-bedrock-guardrails/
  * Adjusted CloudFormation template, to allow for auto-detecting the recording language (EN, ES, DE, ...): https://github.com/typex1/Arch9-2024-frankspiess/blob/main/CloudFormation/CFN_Bedrock-Transcribe-Recording-Summary_multiLanguage.yaml
  * Find the Step Functions workflow graph here: https://github.com/typex1/Arch9-2024-frankspiess/blob/main/img/stepfunctions_graph.svg

* **Use case 2**: "Customer Support Chatbot with Retrieval Augmented Generation (add private documents to your LLM retrieval)"
  * Business problem: you have internal, company specific private data which should be part of the search space that your Chatbot can cover - to answer questions.
  * Solution: this time, a fully open sourced approach consisting of Ollama as a platform, Llama3 as LLM, and ChromaDB as vector datastore.
    * Chroma official website: https://www.trychroma.com/
  * How to deploy using Ollama: https://www.youtube.com/watch?v=FQTCLOUnIzI by Matt Williams
  * Optional: if you like a great user interface, also keeping your chat history, install AnythingLLM on your laptop - https://www.youtube.com/watch?v=4UFrVvy7VlA 
  * Compute Layer used: EC2 instance type "g4dn.xlarge" https://instances.vantage.sh/aws/ec2/g4dn.xlarge

* **Use case 3**: "Offline image analysis"
  * Business problem: Identify objects and situations in pictures, based on human language, e.g. for visually impaired people
  * Solution: Use model "LLaVA" from https://ollama.com/library/llava
  * How to deploy: follow Matt Williams' video "Installing Ollama" https://www.youtube.com/watch?v=e3j1a2PKw1k , and instead of the model mentioned, pick "LLaVA". 

* **Use case 4**: "Clinical decision support" (not shown in the talk due to limited time)
  * Business problem: people in different roles might need secure advice for explaining medical terms, describe the effect of medications and so on.
  * Solution: Stay with the Ollama LM layer running on EC2 or your own hardware, but change the model to either "Meditron" or 
  * How to deploy: follow Matt Williams' video "Installing Ollama" https://www.youtube.com/watch?v=e3j1a2PKw1k , and instead of the model mentioned, pick "LLaVA". 
    

**Further reading, more advanced topics:**
* Add internet search to Ollama, using "SearXNG": https://www.youtube.com/watch?v=GMlSFIp1na0

* Run any GGUF model from Huggingface in Ollama: https://www.youtube.com/watch?v=LQJVz-B_mZI by Matt Williams

* Model Merge (by Arcee.ai https://www.arcee.ai/)
  * Arcee's mergekit creator Charles Goddard explains model merging: https://www.youtube.com/watch?v=IVDNhQIzyIY
  * Examples for merged models: https://huggingface.co/collections/arcee-ai/medical-model-merges-65de7322dd7f4890e749f4a4
  * Arcee merge kit UI on Huggingface: https://huggingface.co/spaces/arcee-ai/mergekit-gui
  * Arcee's models on AWS Marketplace: https://aws.amazon.com/ai/generative-ai/partners/?aws-marketplace-cards.sort-by=item.additionalFields.sortOrder&aws-marketplace-cards.sort-order=asc&awsf.aws-marketplace-aws-marketplace-aim=*all&awsf.aws-marketplace-aim=aws-marketplace-aim%23gen-ai-software-competency-partner&aws-marketplace-cards.q=arcee&aws-marketplace-cards.q_operator=AND
