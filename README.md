# genai
<h1>Generative AI beginner's guide 
</h1>
This beginner's guide introduces you to the core technologies of generative AI and explains how they fit together to power chatbots and applications. Generative AI (also known as genAI or gen AI) is a field of machine learning (ML) that develops and uses ML models for generating new content.

Generative AI models are often called large language models (LLMs) because of their large size and ability to understand and generate natural language. However, depending on the data that the models are trained on, these models can understand and generate content from multiple modalities, including text, images, videos, and audio. Models that work with multiple modalities of data are called multimodal models.

Google provides the Gemini family of generative AI models designed for multimodal use cases; capable of processing information from multiple modalities, including images, videos, and text.

<h1>Content generation</h1>
In order for generative AI models to generate content that's useful in real-world applications, they need to have the following capabilities:

<h1>Learn how to perform new tasks:</h1>

Generative AI models are designed to perform general tasks. If you want a model to perform tasks that are unique to your use case, then you need to be able to customize the model. On Vertex AI, you can customize your model through model tuning.

<h1>Access external information:</h1>

Generative AI models are trained on vast amounts of data. However, in order for these models to be useful, they need to be able to access information outside of their training data. For example, if you want to create a customer service chatbot that's powered by a generative AI model, the model needs to have access to information about the products and services that you offer. In Vertex AI, you use the grounding and function calling features to help the model access external information.

<h1>Block harmful content:</h1>

Generative AI models might generate output that you don't expect, including text that's offensive or insensitive. To maintain safety and prevent misuse, the models need safety filters to block prompts and responses that are determined to be potentially harmful. Vertex AI has built-in safety features that promote the responsible use of our generative AI services.

The following diagram shows how these different capabilities work together to generate content that you want:

<h2>Generative AI workflow diagram</h2>  

![Image](https://github.com/user-attachments/assets/fa0a2785-57e9-4aa6-bd3f-306a8f884f1b)

<h2>Prompt</h2>  
Prompt	
The generative AI workflow typically starts with prompting. A prompt is a natural language request sent to a generative AI model to elicit a response back. Depending on the model, a prompt can contain text, images, videos, audio, documents, and other modalities or even multiple modalities (multimodal).

Creating a prompt to get the desired response from the model is a practice called prompt design. While prompt design is a process of trial and error, there are prompt design principles and strategies that you can use to nudge the model to behave in the desired way. Vertex AI Studio offers a prompt management tool to help you manage your prompts.

<h3>Foundation models</h3>
Foundation models	
Prompts are sent to a generative AI model for response generation. Vertex AI has a variety of generative AI foundation models that are accessible through a managed API, including the following:

Gemini API: Advanced reasoning, multiturn chat, code generation, and multimodal prompts.
Imagen API: Image generation, image editing, and visual captioning.
MedLM: Medical question answering and summarization. (Private GA)
The models differ in size, modality, and cost. You can explore Google models, as well as open models and models from Google partners, in Model Garden.

<h3>Model customization</h3>
Model customization	
You can customize the default behavior of Google's foundation models so that they consistently generate the desired results without using complex prompts. This customization process is called model tuning. Model tuning helps you reduce the cost and latency of your requests by allowing you to simplify your prompts.

Vertex AI also offers model evaluation tools to help you evaluate the performance of your tuned model. After your tuned model is production-ready, you can deploy it to an endpoint and monitor performance like in standard MLOps workflows.

Access external information
Augmentation	
Vertex AI offers multiple ways to give the model access to external APIs and real-time information.

Grounding: Connects model responses to a source of truth, such as your own data or web search, helping to reduce hallucinations.
RAG: Connects models to external knowledge sources, such as documents and databases, to generate more accurate and informative responses.
Function calling: Lets the model interact with external APIs to get real-time information and perform real-world tasks.
Citation check
Citation check	
After the response is generated, Vertex AI checks whether citations need to be included with the response. If a significant amount of the text in the response comes from a particular source, that source is added to the citation metadata in the response.

Responsible AI and safety
Responsible AI and safety	
The last layer of checks that the prompt and response go through before being returned is the safety filters. Vertex AI checks both the prompt and response for how much the prompt or response belongs to a safety category. If the threshold is exceed for one or more categories, the response is blocked and Vertex AI returns a fallback response.

Response
Response	
If the prompt and response passes the safety filter checks, the response is returned. Typically, the response is returned all at once. However, with Vertex AI you can also receive responses progressively as it generates by enabling streaming.
