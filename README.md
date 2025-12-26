# Microsoft-Foundry-AI-Agents-Foundry-IQ-MCP-A2A-Notes
This Repository contains my "Microsoft Foundry: AI Agents, Foundry IQ, MCP &amp; A2A" Course Notes from Udemy

**I) Foundry Primer and Fundamentals**

**A) Introduction to Generative AI and AI Agents**

**B) Introduction to Microsoft Foundry**

**C) Introduction to the Microsoft Foundry SDK**

**D) Difference Between Hub-Based and Standalone Foundry Projects**

**E) Lab: Deploying Microsoft Foundry in Azure Portal (Hands-On Lab)**

**F) Important: Github Repo for Demos!!**

**G) Lab: Deploying OpenAI Model and Foundry SDK Demo (Hands-On Lab)**

**H) Lab: Deploying Claude and Foundry SDK Demo (Hands-On Lab)**

**I) Lab: Microsoft Foundry Extension in VSCode (Hands-On Lab)**

**(II) Microsoft Foundry AI Agents**

**A) Lab: Agent Service Portal Walkthrough (Hands-On Lab)**

**B) Lab: Creating a Basic Agent from Python Code (Hands-On Lab)**

**C) Lab: Creating a Web Searcher Agent (Hands-On Lab)**

**D) Lab: Creating a Code Interpreter Agent (Hands-On Lab)**

**E) Lab: Creating Agent with OpenAPI Tool (Hands-On Lab)**

**F) Lab: Creating a MCP Server Agent (Hands-On Lab)**

**G) Creating a Multi-Tool Agent (Hands-On Lab)**

**H) Lab: Working with Browser Automation Tool (Hands-On Lab)**

**I) Introduction to Foundry Memory Store**

**J) Lab: Assigning Azure Rule to Foundry for Memory Store Lab (Hands-On Lab)**

**K) Lab: Working with Foundry Memory Store (Hands-On Lab)**

**IV) Building an End-to-End RAG Agent**

**A) What is RAG (Retrieval Augmented Generation) ?**

**B) What are Vector Embeddings ?**

**C) What is Azure AI Search**

**D) Introduction to Multi-Modal RAG in Azure AI Search**

**E) Lab: Deploying RAG Infra on Azure (Hands-On Lab)**

**F) Lab: Creating the AI Search Index (Hands-On Lab)**

**G) Lab: Creating the Multi-Modal RAG Agent (Hands-On Lab)**

**(V) API Management and AI Gateway**

**A) API Management as API Gateway in Foundry**

**B) MCP (Model Context Protocol) - Deep Dive**

**C) MCP Server Architecture**

**D) API Management and MCP Servers: Solution Architect's POV**

**E) Lab: Creating an AI Gateway in Foundry Project (Hands-On Lab)**

**F) Lab: Capabilities of AI Gateway (Hands-On Lab)**

**G) Lab: Creating Our Own MCP Server in ACA (Hands-On Lab)**

**H) Lab: Adding Our MCP Server to AI Gateway (Hands-On Lab)**

**I) Lab: Testing Rate Limiting Policy (Hands-On Lab)**




# **I) Foundry Primer and Fundamentals**

# **A) Introduction to Generative AI and AI Agents**

The video begins with a quick look at generative AI and agents, setting the context for the entire course. It provides an introduction to how artificial intelligence has evolved over the years. Artificial intelligence itself is not new—humans have long been fascinated with building systems capable of replicating or even exceeding human intelligence. This journey began around 1956, when early researchers became ambitious about creating intelligent systems. In 1997, the term “machine learning” emerged, aiming to democratize the creation of models that data scientists could build for domain-specific use cases.

By 2012, the era of deep learning arrived. Deep learning enhanced machine learning by becoming more human-like, using neural networks structured similarly to neurons in the human brain. Training models using these neural networks allowed systems to learn in ways that closely resembled human learning. Then in 2021, the era we live in today began: the era of generative AI. Technologies like Copilot, ChatGPT, and Google Gemini gained the ability to create written, visual, and auditory content simply from user instructions.

Zooming out, two major shifts have taken place. First is the democratization of AI technologies. Anyone—not just data scientists—can interact with advanced AI systems using natural-language prompts such as “write an email,” “create an image,” or “edit this text.” Earlier, interacting with AI models required specialized skills, but today anyone can use them through intuitive interfaces. Second is the shift in model behavior. Before 2021, AI models were predominantly predictive. They were probabilistic models designed for tasks like forecasting house prices or predicting numeric outcomes using algorithms like linear regression. They were not built for natural language conversations.

Generative AI changed that. Today’s models are not the best at predicting future stock prices, but they excel at understanding user intent expressed in natural language and responding in the same language. Every generative AI application relies on a foundation: the Large Language Model (LLM). An LLM is a neural-network-based model that processes natural language input, analyzes intent, and generates output. These models consist of an input layer, many hidden layers that analyze different aspects of language, and an output layer. Models like GPT-4 are massive—for example, GPT-4 was trained on roughly 1.4 trillion parameters, highlighting the incredible computational scale required to build such systems. Because this is extremely resource-intensive, most companies cannot build such models from scratch. Instead, they rely on pre-built foundation models from providers like OpenAI and customize them for domain-specific use cases.

The term foundation model refers to a specific version or instance of an LLM—such as GPT-4, GPT-4.1, or Meta’s Llama models. Developers typically do not build these from scratch due to limited resources, expertise, and infrastructure. Instead, they fine-tune them for business requirements and integrate them into production environments. This tuning and integration is where most developers, including us, spend our time.

This brings us to AI agents. To understand agents, the video introduces the concept of compound AI systems—systems that accomplish tasks by combining multiple interacting components. When foundation models are adapted for specific business use cases, they become part of these compound systems. Agents are essentially applications within this ecosystem that not only use LLMs but also interact with tools, APIs, databases, or enterprise knowledge sources as part of their workflow.

Think of an AI agent as a system where the LLM makes planning decisions, unlike earlier systems that relied on rigid, hard-coded logic. An agent can use an LLM to dynamically determine sequences such as: Step 1, call an API; Step 2, fetch information from a knowledge base; Step 3, generate a response. The LLM becomes the “brain,” orchestrating tools, external systems, and workflows in real time. The more freedom the model has to decide the behavior of the system, the more “agent-like” the application becomes. However, there's ongoing debate about fully autonomous agents versus approaches that include human-in-the-loop mechanisms for safety and control. The course will explore how to build such agents and incorporate controlled oversight.

The industry’s journey over the last few years has been fast-paced. Initially, developers built simple chatbots powered by LLMs to mimic ChatGPT—tools that could compose emails or answer questions. But these chatbot-only systems offered limited business value since they performed no operational actions. That realization led to the rise of agentic systems. Organizations began integrating LLMs with individual tools or plugins, often with hard-coded execution flows. But soon they recognized that users interact in diverse ways, and rigid workflows couldn’t support dynamic needs. They needed systems capable of dynamic execution planning—systems that adjust steps based on the user's query instead of being locked into fixed logic. This shift led to today’s agentic AI development practices, where LLMs plan and orchestrate actions at runtime.

In summary, an AI agent consists of three essential components:

A foundation model (an LLM),

Instructions describing how the agent should behave, and

Tools such as APIs, databases, or plugins that extend the model’s abilities.

Together, they form a powerful system capable of understanding user intent, performing reasoning, leveraging enterprise knowledge, calling tools, and executing business logic dynamically. This forms the core of generative AI and agentic AI fundamentals, which sets the stage for the rest of the course.

# **B) Introduction to Microsoft Foundry**

The video begins with an introduction to Microsoft Foundry, focusing on what it is, why it matters, and why there is so much attention around it. The speaker emphasizes that AI is reshaping the world right now—not in years or months, but in real time—and at a very rapid pace. A few powerful statistics help set the context. For every dollar a company invests in AI, the return on investment is 3.7x. When organizations operate at large scale, that multiplier becomes extremely significant.

But despite these impressive statistics, the reality is that organizations still face major challenges. According to data from the Microsoft Work Trend Index and Deloitte case studies, 81% of leaders expect AI agents to become part of their company’s strategy in the next 12–18 months. At the same time, 93% of organizations are experimenting with multiple models, yet almost 70% of generative AI experiments never reach production. This highlights a painful truth: even though AI is changing the world, companies continue to struggle with very fundamental questions about deploying and productionizing AI systems.

Many organizations wonder how to move systems from experimentation into production. It’s easy to run models in a sandbox, chat with them, or build prototypes. But the real questions arise when production-readiness comes into play. Companies need to know how to monitor these systems, how to implement observability, what kind of tracing capabilities they will have, and what service-level agreements they can provide to their customers. They also wonder whether there is an ecosystem that orchestrates everything—tools, agents, models, workflows—under a single platform. These foundational concerns remain unsolved for many enterprises, which is why such a high percentage of generative AI projects fail to reach production.

This leads into the concept of AI agents, described as the new frontier. Initially, when ChatGPT first appeared a few years ago, developers became fascinated with chatbots. Soon, however, they realized a harsh reality: a chatbot alone does not solve a business problem. It only allows a conversation; it cannot execute tasks. Organizations need solutions that actually perform actions and solve workflows. As a result, the industry shifted from chatbots to building multi-step AI agents. But even with agents, the biggest challenge today is productionization—deploying them, governing them, securing them, and ensuring they work at scale.

Previously, tasks were repetitive and execution logic was fully hard-coded—step 1, step 2, step 3. But for better ROI, workflows today must be dynamic. AI systems must be capable of reordering execution based on context: step 2 before step 1, or step 10 before step 3, depending on the complexity of the use case. Modern enterprises require systems that solve complex, multi-step tasks dynamically and intelligently. That is where the industry stands today: trying to develop systems that execute plans generated in real time based on user or business intent. Yet again, over 70% of experiments don't make it into production because these development challenges still persist.

The video then outlines the major pain points. The first challenge is model selection and deployment. Developers must choose the right model—one that fits the business problem while balancing accuracy, cost, and efficiency. The second challenge is building complex agent workflows. Real-world workflows involve integrating multiple tools, plugins, APIs, and enterprise knowledge sources. Organizations must also ensure governance of these tools and maintain control over access and usage.

The third challenge is content safety. Any enterprise AI application must follow responsible AI principles such as fairness, inclusiveness, and transparency. The fourth challenge relates to observability and governance. Once an agent is deployed in production, organizations require real-time monitoring, alerts for failures, and detection of data drift. Most companies still find observability extremely difficult. The final challenge is tool sprawl. Enterprises have multiple tools, datasets, knowledge stores, and APIs scattered across environments. Bringing all of this together in a governed way continues to be a major problem.

The speaker explains that building an LLM-centric application seems simple at a basic level—provide data, give instructions, use a model, and an agent can function. But the complexity explodes when scaling. Enterprises want agents that use multiple tools, multiple plugins, and multiple knowledge sources simultaneously. This creates the first major pain point. The second major pain point is observability. Organizations want real-time visibility into how agents behave with different users, what decisions they make, and when issues occur.

The next part of the video focuses on developer needs based on real experiences. Developers want a platform that lets them rapidly prototype, build, deploy, and share POCs with customers. They need easy experimentation and evaluation—something that lets them test prompts, models, and datasets without waiting for infrastructure provisioning. Ideally, they want the platform to abstract away infrastructure so they can focus solely on business logic. Finally, developers want a secure, scalable, production-ready ecosystem where they can manage applications, agents, interactions, errors, and governance. They also want rich integrations—tools, plugins, enterprise knowledge systems—all connected in one environment.

This is exactly what Microsoft Foundry aims to solve. After discussing the modern AI challenges and statistics, the video introduces Microsoft Foundry as a complete AI ecosystem. It is a Platform-as-a-Service designed to address every problem discussed earlier.

The first major component is the Model Catalog, where developers can deploy models using serverless inferencing. They never pay for idle time—only for tokens used. The catalog includes not only OpenAI models, but also models from Meta, Mistral, Groq, and many others. There are tens of thousands of models available.

The second component is the Agent Service, which allows developers to combine tools, knowledge sources, and foundational models to build production-grade agents with built-in conversation management, chat history, governance, and observability.

Next is Foundry IQ, a state-of-the-art solution for bringing enterprise knowledge into agents through agentic retrieval systems. Knowledge from Microsoft Fabric, OneLake, SharePoint, vector indexes in Azure Cosmos DB, AI Search, and other cloud systems can be connected under one unified plane. This becomes the single source of truth that agents rely on.

Another key component is the tool ecosystem. Agents are only effective when they have access to tools like MCP servers, logic apps, OpenAPI definitions, vector indexes, and more. Foundry allows seamless integration with all these tools.

The platform also supports fine-tuning foundation models using integrated machine learning capabilities. And Foundry includes a powerful Control Plane that provides observability, tracing, and insights into agent behavior, tool interactions, token usage, and much more.

The ecosystem also supports two development paradigms: cloud-native development and fully local development through Foundry Local. The local option has fewer capabilities but still allows end-to-end development of local agents.

Security, compliance, and governance are integrated deeply into Foundry. A new capability called Agent ID allows agents to be published into Microsoft 365 environments. Just like users in Entra ID, agents can have conditional access policies and privileged identity management applied to them. This solves one of the biggest governance challenges enterprises have been struggling with.

There is also close integration with Microsoft Purview for data classification and protection. Since agents need access to enterprise knowledge—documents, presentations, emails, spreadsheets—Purview ensures they only access what they are authorized to access. Highly sensitive data can be protected appropriately.

The video also includes a screenshot showing the model catalog, highlighting that more than 11,000 models are available. The ecosystem includes models from OpenAI, Meta, Mistral, Groq, DeepSeek, and others. Another screenshot demonstrates how agents created in Foundry can be published directly to Microsoft 365 with full governance support.

The visuals also show the wide range of tools and knowledge sources that can be connected: OpenAPI definitions, MCP tools, Bing search plugins, vector indexes, SharePoint documents, Azure Functions, logic apps, and more. The platform supports protocols like the Agent-to-Agent protocol, allowing complex multi-agent systems. It also supports bringing agents created using LangChain, CrewAI, Semantic Kernel, Autogen, Microsoft Agent Framework, or other frameworks. These agents can be containerized, deployed on cloud infrastructure such as Azure Container Apps, and integrated directly into the Foundry ecosystem with full governance and observability.

The Foundry control plane gives insights into deployed agents, token consumption, cost accumulation, and overall system behavior. It also integrates with API Management to control request rates and prevent container overload or crashes. APIs and MCP servers can also be protected using API Management to ensure proper authentication, rate limiting, and governance.

Finally, the speaker summarizes that Microsoft Foundry is more than just a tool—it is a full ecosystem for AI developers. It offers observability, governance, a massive model catalog, enterprise knowledge integration, tool support, and secure production deployment. It represents a complete environment for building the next generation of agentic AI applications.

# **C) Introduction to the Microsoft Foundry SDK**

The video begins by taking a closer look at the Azure AI Foundry SDK, also known as the Microsoft Foundry SDK. The speaker starts by explaining how different SDKs have evolved over time in the Azure OpenAI ecosystem.

Initially, everything revolved around the Chat Completions API. This API was lightweight, powerful, and stateless. It was excellent for making direct calls to GPT engines and other large language models, but its purpose was limited to generating responses. It did not offer features needed for building more complex agent-like systems.

The next evolution was the Assistants API. This API was stateful and allowed developers to manage conversation threads, making it more suitable for building assistant-style applications. It supported OpenAI models and offered deeper capabilities such as thread management, integration with tools like file search, code interpreter, and function calling. While assistants were more advanced than simple text completion, they were still not full-fledged agents—more like an early or simplified version of the agentic systems we see today.

However, the earlier APIs had two major limitations. First, they lacked strong integration with external plugins, tools, and enterprise knowledge bases. Second, developers could use only OpenAI models; the APIs did not support building agents on top of alternative models such as LLaMA, Mistral, Cohere, or other providers. As organizations started adopting multi-model and multi-cloud strategies, these limitations became significant obstacles.

This is where the Microsoft Foundry SDK comes in. It retains all the capabilities of the Assistants API but extends them dramatically. It provides deep, native integration with tools such as OpenAPI definitions, Logic Apps, Azure Functions, SharePoint, and Microsoft Fabric. More importantly, it allows developers to build agents using any model deployed in the Model Catalog—whether from OpenAI, Meta (LLaMA), Mistral, Cohere, or others. This makes it far more flexible and future-proof.

The Microsoft Foundry SDK is described as a comprehensive toolchain that simplifies building AI applications on Azure. It provides seamless access to popular models from various providers, supports powerful combinations of models, data, and AI services, and works hand-in-hand with the Foundry platform. Because the SDK is closely integrated with the Foundry PaaS ecosystem, it includes built-in capabilities for agent evaluation, debugging, safety checks, and quality improvement across development, testing, and production.

Tasks that previously required hundreds of lines of glue code—manually wiring models, tools, prompts, and workflows—can now be accomplished with just a few lines using the Foundry SDK’s agent services. This dramatically improves developer productivity and eliminates the need for heavy data plumbing when building agents using the older Chat Completions or Assistants APIs.

To use the Foundry SDK for Python—which is the focus of the course and the language used throughout the video series—you only need to install a single package. Running a simple command in the terminal installs azure-ai-projects, the core Foundry SDK, into your Python environment. The setup is minimal, and once installed, you can immediately start building agents.

The speaker concludes by summarizing that this introductory video was focused on explaining the background and purpose of the Microsoft Foundry SDK. With that foundation established, the session transitions to the next set of videos in the series.

# **D) Difference Between Hub-Based and Standalone Foundry Projects**

This video discusses the differences between hub-based projects and standalone Microsoft Foundry projects. This is an area where many people get confused, and the speaker mentions that even they initially got tangled in the small details before eventually understanding how everything fits together. The goal of the video is to clearly explain those differences.

From a strategic viewpoint, the Microsoft AI ecosystem has several layers. When the speaker created their first course, it was focused on Azure OpenAI, where users relied on the Azure OpenAI Studio to deploy models through serverless inferencing APIs and then interact with them via the Chat Completions API. That ecosystem still exists today and remains an important foundation that powers much of Azure AI Studio. However, it was never designed for team collaboration or to provide a unified development experience across multiple applications.

The speaker then talks about Microsoft Copilot Studio. This was designed as a low-code tool mainly for citizen developers. It enables people to extend their Microsoft 365 Copilot experience using custom agents. This is also an important component of the Microsoft AI world.

But the real focus of the video is the Azure AI Studio ecosystem. This environment is geared toward collaboration, operational workflows, and the entire development lifecycle for LLM-centric applications and agentic systems. Azure AI Studio provides strong monitoring capabilities for deployed generative AI applications—not only after deployment, but also before deployment while building, testing, and debugging. This is the primary environment where developers will spend their time, and it is the main area of interest in the course.

The speaker then explains what happens when you go to portal.azure.com, search for “foundry,” and click the Microsoft Foundry option. When you reach that page, you see two icons. One has a purplish logo labeled “Foundry,” and the other has a blue-reddish logo labeled “AI Hubs.” The purplish logo represents the standalone Foundry project, while the blue-reddish one represents the hub-based Foundry project. Both exist in the Microsoft AI ecosystem, but they serve very different purposes, which contributes to the confusion.

To clarify, the speaker introduces a visual comparison. The left side represents the AI hub (the hub-based Foundry project), and the right side represents the standalone Foundry project. Both of these use the Azure AI Projects SDK (also referred to as the Microsoft Foundry SDK). However, hub-based projects are supported only by version 1 of the Foundry SDK. Standalone Foundry projects, on the other hand, are supported by version 2 of the Foundry SDK.

Another key difference is the intended use case. Hub-based Foundry projects are meant for cross-team collaboration, whereas standalone Foundry projects are meant for single-team, focused environments. When you deploy a hub, you can create multiple projects inside the hub, and these are different in structure from standalone projects. The hub operates at the organization level, while the projects inside operate at the team or department level.

The hub can also maintain connections to various Azure services—Azure OpenAI, Azure Cognitive Services, AI Search, Azure Key Vault, and Azure Storage. These connections can be defined at two levels. If defined at the hub level, they propagate to all projects within the hub. If defined at the project level, they remain private to that project only. This creates a layered infrastructure model where several components must be managed either at the hub level or at the individual project level for the hub-based approach to work properly.

On the right side of the visual, standalone Foundry projects appear much simpler. They do not have the underlying infrastructure layers that hubs require. They still support connections to SharePoint, Fabric, AI Search, Azure Storage, Azure Functions, and Azure Cognitive Services, but these connections belong exclusively to the standalone project. The standalone approach avoids the overhead of managing hub infrastructure while still supporting powerful integrations.

The speaker shows another visual highlighting that hub-based projects deploy additional underlying resources, which creates infrastructure management overhead. Standalone Foundry projects do not require this overhead, making them easier to work with. The speaker emphasizes that the two approaches are designed for different scenarios. Hub-based architectures are meant for large organizations needing centralized visibility across multiple departments. Standalone Foundry projects are ideal for lean teams, startups, or developers adopting cutting-edge features without dealing with legacy systems.

The hierarchy of a hub-based project is also explained. At the top sits the AI Hub at the organizational level. Within the hub are multiple projects functioning at the department level. Each project can apply its own role-based access control for validated users. Connections defined at the hub level are shared across all projects within the hub, while connections defined at the project level remain private to that project.

Another comparison slide reinforces these points. In terms of scope, the hub-based approach operates at the organizational level, while the standalone approach is meant for specific initiatives and small teams. For collaboration, the hub-based model supports multi-team and cross-department collaboration. The standalone model is designed for focused, independent teams.

The speaker also clarifies that hub-based projects are accessed through the classic Microsoft Foundry portal, while standalone projects function through the new Microsoft Foundry portal. This is an important distinction for navigation and feature availability.

There are also differences in feature support. For example, if you want to deploy models on your own infrastructure—such as hosting open-source models from Hugging Face—that capability is available only in hub-based projects. Standalone Foundry projects do not support infrastructure-level model hosting. Similarly, the Azure Content Understanding service, especially in its full end-to-end capability across videos, images, and multimodal inputs, is available only within hub-based projects.

Another major feature difference is Prompt Flow, a low-code microservice for building prompt-based AI pipelines. This is extremely useful when working with non-technical stakeholders or when presenting solutions. Prompt Flow is available only in hub-based projects and not in standalone Foundry projects.

The speaker then shares information about their courses. For learning Microsoft Foundry standalone projects, they recommend the course titled Microsoft Foundry Agents MCP2 and Foundry IQ. A link will be available in the presentation resources. Similar details can be accessed from the instructor’s Udemy profile.

For learning the hub-based approach—including Prompt Flow, LLMOps, RAG, the Azure AI Agent Service, Microsoft Agent Framework, Semantic Kernel SDK, and Azure Content Understanding—the speaker has two separate courses, also available via Udemy or through the links provided in the presentation.

The video concludes by summarizing that these are the major differences between the hub-based and standalone project approaches in Microsoft Foundry. With the explanation complete, the speaker transitions to the next set of videos.

# **E) Lab: Deploying Microsoft Foundry in Azure Portal (Hands-On Lab)**

In this video, we will first deploy a Microsoft Foundry standalone project resource in Azure.com, and then we’ll take a quick walkthrough of the entire AI Foundry portal and its ecosystem so that we can set the pace for the upcoming modules in the course.

I’m on Portal.azure.com, and I’ll start by going to the search bar and searching for Microsoft Foundry. When you click on Microsoft Foundry, you will notice two options on the left-hand side of the screen. The first one shows the new Foundry logo, while the second one has the old Foundry logo and is labeled AI Hubs. The second option represents the classic experience, where you first create a hub and then a project, meaning the project exists within a hub — this is called a hub-based project. However, for this course, we will follow the first route using the new Foundry experience, which allows creating a standalone project that does not sit inside any hub. This is the environment where the new Microsoft Foundry portal operates.

Next, I’ll go to the Foundry section, click on Create, and start by creating a new resource group. I’ll name this resource group Foundry Demo RG. Then I’ll name the Foundry project as Udemy Demo Project. For the region, I’ll select Sweden Central. Sweden Central works reliably for me every time, and I’ve made it a habit to use it. You can choose any other region, but it’s important to note that some models are not available in all regions. For example, if you want to deploy GPT-4 or GPT-4.1, you must check the documentation on Microsoft.com to ensure that your selected region supports those models. For this demo, I’ll continue with Sweden Central since it always works for my use cases.

We have created the resource, and we’ve named it. But we also want to name our project. So I’ll set the project name as Udemy Demo Project—using “Prog” instead of typing the full word “Project”. This resource will contain one project, but remember, this is not a hub like the classic method. It is simply a resource containing a single default project.

After that, I’ll click Next repeatedly because there is nothing additional we need to configure for storage, networking, identity, encryption, or tags. Once done, I’ll hit Create, and within a few seconds the resource gets deployed. I click Go to resource, and that brings me into the Foundry resource overview page.

To navigate to the project itself, I look for the button that takes me into the studio or Foundry portal. And there it is — Go to Foundry Portal. Clicking it opens the new Foundry experience. This is the new interface for standalone projects. If you wanted to work with hub-based projects, you would switch back to the classic portal using the toggle. But since we’re working with standalone projects, we will stay in the new experience.

Here, you will see your project endpoint, which will be crucial later when we start writing Python code. The endpoint and the project API key are both required to authenticate our Python clients and connect code to our Foundry resources.

Moving on to the Discover tab — this is where you explore all the models you can deploy. There is also a dedicated Models area. This is the model catalog I mentioned earlier, and it contains tens of thousands of models. You will see around 11,000+ models available for deployment as serverless inference endpoints. Some of the major models available include Claude Opus 4.5, Claude Sonnet 4.5, GPT-5.1, GPT-5.1 Codex, DeepSeek, the latest video generation models, Grok from X, and several Microsoft models like the Model Router and DeepSeek 3.1.

Another very useful feature here is Compare Models. Clicking on Compare Models allows you to evaluate multiple models against each other based on metrics like accuracy, precision, quality, safety, cost, and throughput. So if your goal is cost optimization and you don’t care too much about precision or recall, you can compare models directly and make a decision easily. For example, you can compare GPT-5.1, Claude Opus 4.5, and Claude Opus 4.1. When comparing them, you’ll notice that Claude Opus 4.1 clearly wins in terms of quality, safety, estimated cost (it's cheaper), and throughput.

You can also compare other aspects, such as whether a model is multimodal. Both Claude Opus models are multimodal for inputs — they support text, images, and code — but they output only text, not images. In terms of context window, all three models allow around 200,000 tokens, but Claude Opus 4.1 has a smaller max output of 32,000 tokens. GPT-5.1 performs better here. You can also check each model’s training cutoff date to understand its knowledge recency.

Regarding endpoints, if you want to use the OpenAI SDK with Chat Completions API, the Claude models will not work — they are not compatible. In that case, you must use GPT-5.1. But if you are building agents, all three models work perfectly. Supported features include streaming, reasoning, summaries, and tool calling. Fine-tuning is not available for any of these models because they are very large and computationally expensive. Multimodal input support is available, but multimodal output is not.

Next, moving to the Tools section — this is the MCP server registry. MCP stands for Model Context Protocol. This registry contains verified MCP servers built by Microsoft partners and vendors. Some examples include Cosmos DB for PostgreSQL, Elasticsearch, Azure Databricks, MongoDB, Genie, Vercel, Atlassian, plus MCP servers for Azure Language and Azure Speech. This is a great place to bring external tools directly into your agent workflows.

Now let’s move to the Build section. Here you get dedicated areas for building agents, building workflows, viewing all deployed models, fine-tuning (if supported), managing tools like OpenAPI definitions or MCP servers, configuring enterprise knowledge sources, importing external vector indexes, and building knowledge bases for agent retrieval systems. You also have sections for data assets, evaluations (to measure agent performance), and guardrails to configure content safety policies using responsible AI principles.

At this stage, I don’t have any agents, models, or tools deployed yet, but we will build all of these in upcoming demos.

Next is the Operate area — this acts as the control plane of Microsoft Foundry. It provides observability and governance. Here you can see active alerts, whether any jailbreaking attempts were made, or whether agents published into Microsoft 365 violated conditional access, information protection, or data loss prevention policies. This area integrates closely with Microsoft Purview and Microsoft Entra ID.

You can also see operational analytics: running agents, cost estimates, agent success rate, total token usage, and agent run volume over time via time-series dashboards.

Then comes the Assets section. This shows all deployed agents, their Entra ID, deployed models, tools added to the environment, and the compliance dashboard for Defender and Purview integrations. You can configure content safety guardrails here, monitor security posture using Defender for Cloud recommendations, and view your cloud workload protection plan.

The Quota segment displays your model quotas — for example, GPT-4 may have 10,000 tokens per minute, and other models like Phi or Sora may have different limits. You can also check deployment allocations and request-per-minute limits.

Finally, in the Admin section, you can view all projects inside the resource. There is also an AI Gateway area that becomes important when we integrate with Azure API Management. In later labs, we will use API Management to apply rate limits, governance, and monitoring for agents, MCP servers, and OpenAPI tools.

This completes a full walkthrough of the entire new Microsoft Foundry portal. We’ve covered everything at a high level. Without further delay, let’s proceed to the next set of videos.

# **F) Important: Github Repo for Demos!!**

Gave GitHub Repository Link for the demos

# **G) Lab: Deploying OpenAI Model and Foundry SDK Demo (Hands-On Lab)**

In this video, we begin with the first lab, starting with very basic concepts and gradually ramping things up. The goal of this lab is to deploy an OpenAI chat completion model—specifically GPT-4 (or any other supported chat completion model)—and interact with it using both the Microsoft Foundry portal and code via the Microsoft Foundry SDK (version 2).

To begin, the GitHub repository has already been cloned into the VS Code environment. For this lab, we work inside the Getting Started folder. Within it, we navigate to OpenAI Chat Completions and open the Jupyter Notebook named chat_completions.ipynb, which will be used for the demo.

Next, we move to portal.azure.com, navigate to the Foundry project inside the Microsoft Foundry portal, and land on the Discover section. The first task is to deploy a GPT-4 model. We go to the Models section, search for GPT-4, and select it. If GPT-4 is unavailable in your region, any OpenAI model categorized as a chat completion model can be used instead.

After selecting the model, the model details page displays information such as benchmarks, quality index, latency, and estimated cost. GPT-4 costs approximately $4.38 per million tokens, which is on the higher end compared to other models. However, since this lab does not involve long-running workloads, cost is not a major concern. The model is deployed using default settings, and once deployment completes, the portal automatically opens the Chat Playground.

Deploying with default settings means the model is provisioned with a 50,000 tokens-per-minute rate limit, default content safety guardrails, and a Global Standard deployment type. Global Standard is a serverless option where you pay only for the tokens consumed. This is ideal for proofs of concept and development work.

Another deployment option is Global Provisioned Throughput, which is intended for production workloads. In this mode, tokens are purchased in advance, providing predictable performance, higher SLAs, and potential cost savings. While Global Provisioned Throughput is better for production scenarios, Global Standard is recommended for experimentation and development.

Once deployed, the model appears in the Build → Models section. Clicking the model opens the Chat Playground, where instructions can be defined (for example, “You are a helpful AI assistant”). You can also connect tools such as a code interpreter, although advanced features like tools, memory, or knowledge bases require creating an agent, which will be covered in later labs.

A simple prompt such as “Hi, my name is…” produces a response from the model. The interface also displays performance metrics such as response time, input tokens, output tokens, and total token usage. Additional tabs provide access to the model’s endpoint URI, authentication keys, monitoring metrics, estimated costs, and evaluation tools to assess whether the model fits a business use case.

After validating the model in the playground, the next step is calling it from code. In VS Code, environment variables must be configured, including the model deployment name (for example, gpt-4) and the Foundry project endpoint, which can be copied from the Foundry portal home page. These environment variables are saved before proceeding.

Inside the Jupyter notebook, the Azure AI Projects SDK (Foundry SDK v2, pre-release) is used. This SDK works only with standalone Foundry projects and does not support hub-based projects. The notebook also installs required dependencies such as openai, python-dotenv, and azure-identity. Environment variables are loaded from the .env file, and a Foundry Project Client is initialized.

Before running the notebook, Azure authentication is required. This is done by opening the integrated terminal in VS Code and running az login, ensuring that the Azure CLI is installed. After signing in and selecting the correct subscription, the Foundry Project Client is authenticated using the logged-in credentials.

Once authenticated, the OpenAI client is initialized from the Foundry Project Client. This client is specifically used for OpenAI models that rely on the chat completions API. Models from other providers (such as DeepSeek or Claude) require different clients, which will be covered in later labs.

Finally, a request is sent to the model using the Chat Completions / Responses API. The system prompt defines the assistant’s behavior, and a user prompt such as “Can you tell me about Microsoft Foundry?” is sent. The response is printed, confirming that the GPT-4 model is successfully deployed and callable through code.

With this, the first lab is successfully completed. The OpenAI GPT-4 model is deployed, tested in the Foundry Chat Playground, and invoked programmatically using the Foundry SDK v2. The next videos will build on this foundation and introduce more advanced concepts.

# **H) Lab: Deploying Claude and Foundry SDK Demo (Hands-On Lab)**

In this lab, we deploy a Claude model from the Foundry Model Catalog and invoke it using Foundry SDK v2 concepts, specifically through the Anthropic SDK. For this exercise, we navigate to Getting Started → Foundry Catalog Completions, where we find a .env file and a Jupyter notebook that contains the main codebase.

Before calling the model via code, the first step is to deploy the Claude model. From the Discover page in the Foundry portal, we search for Claude. Two options are available, and for this lab, we proceed with Claude Opus 4.5. The model is deployed using the default settings, and the selected industry is Education.

In terms of pricing, Claude Opus 4.5 is extremely cost-effective. It costs approximately $0.005 per million tokens for input inference and $0.025 per million tokens for output inference under the pay-as-you-go model. After agreeing to the terms, we proceed with deployment and wait for the model to be fully provisioned.

Once deployment starts, the model initially remains in the Creating state. Attempting to interact with it during this phase results in an error indicating that the API deployment is not yet ready. After waiting for about a minute, the deployment succeeds, and the model becomes available. At this point, a simple test prompt such as “Hi, my name is…” confirms that the model responds correctly in the playground.

With the model successfully deployed, we move on to configuring the environment variables. Unlike the previous lab where the Foundry SDK was used directly, this lab uses the Anthropic SDK. Therefore, we need three key values: the model endpoint, the model deployment name, and the API key.

To retrieve these values, we return to portal.azure.com and open the model in the playground. Next to the Chat option, there is a Code tab. From here, we copy the model endpoint, which is used for API calls. This endpoint is specific to the deployed model and is different from the Foundry project endpoint. The model deployment name is set to ClaudeOpus45, and the API key is obtained by clicking the key icon in the portal.

After copying the endpoint, deployment name, and API key into the .env file, the changes are saved. The notebook uses Anthropic SDK version 0.75.0. Before executing the code, the Python kernel is restarted to ensure a clean environment.

The notebook begins by loading environment variables from the .env file. Using the model endpoint and API key, an Anthropic Foundry client is created. This client establishes a secure connection between the Anthropic SDK and the Foundry project resource.

Once the client is initialized, the Messages API is used to send a request to the model. The system prompt defines the assistant’s behavior as a helpful translator from English to Spanish. The user prompt requests the translation of a simple sentence: “Hi, my name is, how are you today?” The maximum output tokens are set to 1024.

After receiving the response, it is converted into a dictionary, and the translated output text is extracted. The model successfully returns the Spanish translation, confirming that the deployment and code integration are working as expected.

With this, the lab concludes successfully. We deployed an out-of-the-box Anthropic model (Claude Opus 4.5) from the Foundry Model Catalog and invoked it programmatically using the Anthropic SDK. Having validated both deployment and inference, we are now ready to proceed to the next set of videos.

# **I) Lab: Microsoft Foundry Extension in VSCode (Hands-On Lab)**

In this video, we explore how to work with Microsoft Foundry directly inside VS Code using the Foundry extension from the VS Code Marketplace. This allows you to interact with Foundry resources in a code-native environment without constantly switching to the Azure portal.

To get started, open VS Code and navigate to the Extensions Marketplace. The first extension to install is the Azure Resources Extension. Once installed, open the extension and click the plus (+) icon to sign in with your Azure account. After signing in, VS Code automatically loads all resources available across your Azure subscriptions.

Once the Azure Resources extension is set up, return to the Extensions Marketplace and search for Microsoft Foundry. Install the Foundry extension in your VS Code environment. After installation, opening the extension presents a dedicated Foundry pane where you are automatically signed in using your Azure credentials.

Within the Foundry extension, you can view various components such as Models, Agents, the Model Catalog, the Model Playground, and the Local Agent Playground. Expanding the Models section displays all the models deployed within your Foundry project. Selecting a model, such as a Claude model, opens its detailed view, including information like the target URI, authentication keys, and other configuration details.

To interact with a model directly, open the Model Playground within VS Code. From the model selector, choose your deployed model—for example, Claude Opus 4.5. This loads the model into the playground, enabling chat-based interaction similar to the experience in portal.azure.com.

In the playground, you can define a system prompt, such as setting the assistant to be a helpful AI assistant. You can also configure parameters like temperature and maximum response tokens. Once configured, submitting a prompt returns a response from the model in real time.

The Foundry extension also supports agents. Once agents are created, they appear under the Declarative Agents and Hosted Agents sections. These agents can be tested using the Remote Agent Playground, similar to how models are tested in the Model Playground. Since no agents are configured at this point, the remote agent playground is not demonstrated in this video.

Overall, the Foundry extension in VS Code mirrors much of the experience available in the Azure portal, while providing it directly within a developer-friendly, code-centric environment. This makes it easier to manage models, experiment with prompts, and work efficiently without leaving VS Code.

With that, this short walkthrough of the Foundry VS Code extension concludes. In the next videos, we will continue building on this foundation and explore more advanced capabilities.

# **(II) Microsoft Foundry AI Agents**

# **A) Lab: Agent Service Portal Walkthrough (Hands-On Lab)**

In this video, we’ll do a quick walkthrough of the Agents section in the Microsoft Foundry portal. We’ll create our very first demo agent using the portal’s graphical user interface and get started with the agent service quickly.

I’m currently on the Microsoft Foundry portal, inside the Build area. On the left-hand side of the screen, the very first option you’ll see is the Agents section. This is what we’ll use to build our agent. When I click on Create Agent, I can name the agent. I’ll name it Demo Agent and then click on the Create button.

Once the agent is created, the next step is to power it with a Foundation Large Language Model. You can choose from different models—OpenAI models, Anthropic models like Claude Opus 4 or 5, and others. The choice is completely up to you. For this demo, I’ll go ahead with GPT-4.

After selecting the model, you can provide instructions to your agent. I’ll keep it simple and type:
“You are a helpful AI assistant.”
After entering the instruction, it’s important to click the Save button. This saves the configuration and creates version two of the agent.

A new capability added to the Microsoft Foundry agent service is agent versioning. Earlier, there wasn’t a way to track or revert to previous versions of an agent. Now, every time you click Save—whether through the GUI or a code-first environment—the agent version increments automatically. This allows you to go back in time, view older versions, and even compare them. It’s similar to how versioning works in Docker Hub or container registries.

After saving, you can test the agent by typing a message. For example, I type:
“My name is Joe. Nice to meet you.”
The agent responds appropriately:
“Nice to meet you too. How can I assist you today?”

You can also see token usage details, such as input tokens (27) and output tokens (19). Additionally, there is an AI Quality section. When you open it, you’ll find metrics like Intent Resolution and Task Adherence, both of which return a binary pass or fail status. In this case, both pass.

If you click on the Debug button, it opens the Trace view, which is powered by OpenTelemetry. This forms a crucial part of observability and tracing within the Foundry control plane. Here, you can see the Conversation ID, trace ID, span ID, and other unique identifiers associated with the interaction.

The Conversation ID is particularly important. In hub-based projects, this concept existed as threads. In standalone projects, the built-up version of threads is what we now call a conversation ID. It stores the entire interaction history between the user and the agent, including both user inputs and agent responses.

You can store this conversation ID in a key-value store such as Redis. When a user comes back in a new session, you can retrieve that conversation ID and continue the interaction seamlessly. This helps preserve context across multiple sessions.

Within the trace, you can see the input, output, metadata, attributes (which combine user input and agent output), and usage details like prompt tokens, completion tokens, and total tokens.

The Evaluation section provides deeper insight into AI quality. For example, Intent Resolution scores how well the agent understood the user’s intent. In this case, it scores 5 out of 5 because the user’s intent was simply a greeting, and the agent responded correctly.

Task Adherence evaluates whether the agent followed the required steps to complete a task. This becomes especially important when tool calls are involved—such as APIs, enterprise knowledge retrieval, or multi-step workflows. Even though this example was simple, the agent still scored 5 out of 5 for task adherence.

Moving on to Tools, you can enhance your agent with several built-in capabilities. These include file search, code interpreter, Azure AI Search grounding, Bing search, computer use, browser automation, Fabric data agent integration, and SharePoint document access.

The Code Interpreter allows the agent to generate and execute Python code in a sandbox environment, which is useful for tasks like generating charts. Azure AI Search enables retrieval-augmented generation (RAG) using vector indexes built on enterprise data.

In the Knowledge section, you can connect your agent to Foundry IQ. Foundry IQ is a powerful system that deserves its own deep dive, and there will be a dedicated section covering it later.

There is also a Memory Store, which retains context to personalize interactions. A memory store is auto-created and uses the deployed model. It helps persist user memory across sessions. While conversation IDs are the simplest way to retain history, memory stores offer advanced capabilities such as summarization and internal vector search.

You can also attach Guardrails and Content Filters to control thresholds for sensitive content such as sexual material, hate speech, or jailbreaking attempts.

In the YAML section, you can view the agent definition. This agent is currently a prompt-based agent using GPT-4 with no tools attached. You can compare YAML files across different versions to see how the agent has evolved. There’s also a Code section that provides a starter snippet to call the agent.

Next, let’s see tools in action. I add the File Search tool and upload a PDF from a GitHub repository—specifically, a document titled Carbon Ops ESG Intelligence Model. Foundry automatically creates a small, temporary vector index optimized for retrieving information from this document.

Once indexing is complete, I start a new chat and ask:
“Tell me something about the Carbon Ops ESG Intelligence Model.”

The agent analyzes the uploaded document, retrieves relevant information, and provides a summarized response. It also shows the document chunk used, the tool invoked (file search), and total token usage (5,496 tokens).

In the Trace view, you can see that the response involved a tool call. The metadata includes the file ID, file name, and a relevance score (0.033). This score indicates how relevant the document was to answering the query and becomes critical when multiple documents are involved.

After this, I save the agent again, creating version three.

In the Tools section, you can connect additional services such as Fabric Data Agent, SharePoint sites, browser automation, and MCP servers. Supported MCP servers include Azure Cosmos DB, Databricks Genie, MongoDB, Elasticsearch, Azure Managed Redis, and more. You can also register custom MCP servers or bring in APIs using OpenAPI specifications. Agent-to-agent tools are also supported.

Finally, in the Knowledge section, you can fully leverage Foundry IQ to index enterprise knowledge from OneLake, SharePoint, and Microsoft 365 using Azure AI Search—all in one place.

That wraps up the video. We covered a complete walkthrough of the Microsoft Foundry Agent Service, created a demo agent, explored versioning, conversation IDs, memory stores, observability, tracing, evaluation, and tool usage, including file search in action.

# **B) Lab: Creating a Basic Agent from Python Code (Hands-On Lab)**

In this lab, we’ll try out the Microsoft Foundry Agent Service in a code-first environment. Instead of using the portal UI, we’ll create and manage our agent using the Microsoft Foundry SDK. Once created, the agent will also be visible in portal.azure.com and Foundry Studio. We’ll focus on setting everything up using code and understanding how Conversation ID helps maintain conversation history for the agent.

The lab’s codebase is located under Agent Service → Getting Started, and the notebook inside that directory is what we’ll run for this lab. Along with that, we’ll be filling in required environment variables inside a .env file.

The first step is to set up the environment variables. We need two things: the Foundry Project Endpoint and the Model Deployment Name. This step is repetitive, so it may be skipped in some videos to avoid unnecessary length, but it’s important to understand. Once you do it a couple of times, it becomes second nature.

To get the project endpoint, we go to Foundry Studio, navigate to the Home section, and copy the Project Endpoint along with the Project API Key. Next, we need the model deployment name. For that, we go to the Build area and open the Models section. In this lab, we’re building the agent on top of GPT-4, though you could also use Claude or any other supported foundational model.

Once the environment variables are set, we’re ready to run the Python notebook. The notebook uses the Azure AI Projects SDK (Foundry SDK v2.0.0-beta.2) along with the OpenAI SDK, python-dotenv, and Azure Identity. Initially, we load the environment variables from the .env file and initialize a Foundry Project Client, which allows the notebook to connect to Foundry Studio and create resources inside the Foundry Agent Service.

Next, we create our agent—this time, a Batman agent. This is a fun example and a childhood dream coming true: being able to converse with Bruce Wayne in real time. The agent name is Batman Agent.

To create the agent, we use the project client and call project_client.agents.create_version. This creates a new version of the agent. Since we’re creating it for the first time, this becomes version one. Each time this code block runs, it automatically creates a new version of the agent.

While creating the agent, we provide the agent name, the model deployment name (GPT-4 in this case), and the system prompt. The system prompt defines the agent’s behavior:

“You are Batman, the Dark Knight of Gotham City. Respond to all queries in character as Batman would.”

Once the agent is created, we receive the Agent ID and the version number, which confirms that version one of the Batman agent has been successfully created.

Next, we set up the conversation system. For this, we create an OpenAI client. The OpenAI client is required to retrieve responses from the agent using the Chat Completions API. This works because we’re using GPT-4. If we were using Claude, we’d need the Anthropic SDK instead.

We then create a conversation object, which stores the chat history between the user and the agent. This returns a Conversation ID, which we’ll reuse for all subsequent interactions to maintain context.

After that, we set up a while loop for the chat. As long as the user input is not exit or quit, the loop continues running. Inside the loop, we send the user input to the agent using the OpenAI Chat Completions API, along with the conversation ID and the agent reference. By default, the latest version of the agent is used.

The first user query is:
“My name is Kojo Singh Bakshi. And how is Gotham?”

Gotham, of course, is the city Batman protects. The agent responds in full Batman character, describing Gotham as dark, dangerous, and filled with corruption—but reassuring that it’s still under his protection. The response is very “Batman-ish,” confirming that the system prompt is working as intended.

To demonstrate Conversation ID in action, we ask a follow-up question:
“Can you tell me what my name was?”

Because the agent has access to the previous conversation history via the conversation ID, it correctly remembers the name given earlier. The response is dramatic, as expected from Batman, but it accurately recalls the name Kojo Singh Bakshi, proving that conversation history is being preserved across messages.

This confirms that Conversation ID allows the agent to maintain context across multiple user interactions within the same session.

Finally, we type exit, which ends the chat loop and exits the program.

Before concluding the video, we verify whether the agent was created in the Foundry Portal. Navigating to the Agents section, we can see Batman Agent – Version 1 listed there. If we open the Traces section, we can view the conversation ID and the complete trace of the interaction, including user inputs and agent outputs.

The total number of tokens consumed during the conversation is 219 tokens. The first run consumed 139 tokens, and the second run used more tokens because the conversation history increased the token count. This highlights an important consideration when building systems at scale: token inflation due to chat history. Managing this efficiently becomes critical in production environments.

That concludes the demo for this lab. We successfully created an agent in a code-first environment, validated conversation history using Conversation ID, observed tracing and token usage, and confirmed the agent’s presence in the Foundry Portal.

# **C) Lab: Creating a Web Searcher Agent (Hands-On Lab)**

In this lab, we’ll be creating a Web Searcher Agent in Microsoft Foundry using the Foundry SDK in a code-first environment. To perform this lab, we navigate to the web-search folder located inside the agent-service directory. This folder contains a Python notebook and a .env file where we configure the required environment variables.

The environment variables have already been set, including the Foundry Project Endpoint and the Model Deployment Name. For this lab, the model deployment used is GPT-4.

The goal of the web searcher agent is straightforward. We want to create a Foundry agent and give it access to the Web Search tool, which is already available in the Microsoft Foundry ecosystem. Everything in this lab is done programmatically using the SDK.

When a user query such as “Tell me about the latest trends and advancements in renewable energy” comes in, the query is sent to the Foundry agent. The agent analyzes the intent of the query, evaluates the available tools, invokes the Web Search tool, retrieves real-time information from the web, and finally summarizes that information into a response for the user.

We begin by loading the environment variables from the .env file—specifically the Foundry project endpoint and the model deployment name. After that, we initialize the Foundry Project Client, which allows our code to connect to the Foundry portal and interact with the agent service.

Since this agent is based on GPT-4, an OpenAI model, we also need to create an OpenAI client. This client is responsible for sending messages to the agent and receiving responses. The OpenAI client is created using the Foundry project client initialized earlier.

Next, we create the agent itself. To do this, we use project_client.agents.create_version. The agent is named Web Search Agent. In the agent definition, we provide the GPT-4 model deployment name, an instruction set, and a tools array. Inside the tools array, we grant the agent access to the Web Search tool.

The system prompt for the agent is simple and clear:
“You are a helpful assistant that uses web search to answer user queries.”

Once the agent is created, we receive an Agent ID, which we then use to create a conversation object. This conversation object allows us to maintain a conversation history and returns a Conversation ID that will be used for subsequent interactions.

With the conversation object in place, we send a user query to the agent:
“What are the latest advancements in renewable energy?”

This query is sent using the OpenAI Client Responses API, along with the conversation ID and a reference to the agent. Importantly, the user query itself does not explicitly instruct the agent to use the web search tool. Instead, the agent autonomously analyzes the intent of the query, evaluates the available tools, and decides to invoke the Web Search tool.

This behavior highlights the power of the Foundry agent architecture. The agent independently determines when a tool should be fired based on user intent and system configuration. In this case, it correctly invokes the web search tool to retrieve up-to-date information.

The response indicates that the renewable energy sector has seen several key advancements as of 2025. It covers topics such as next-generation solar panels, including bifacial solar panels, advancements in photovoltaics, and low-cost renewable energy technologies. The response also includes links to the websites used as grounding sources.

By navigating to these links, we can verify that the agent retrieved real information from the web. For example, the sources discuss cost-effective photovoltaics and bifacial solar panels, confirming the accuracy of the retrieved content.

Each of these URLs is shown as part of the grounding knowledge used by the agent. This transparency helps validate the response and understand where the information originated.

Next, we move to the Foundry Portal to validate what happened behind the scenes. In the Agents section, we can see Web Search Agent – Version 1 listed. The agent clearly shows that it has the Web Search tool attached.

If we inspect the agent’s YAML definition, we can confirm that the web search preview tool is present under the tools configuration.

Moving to the Traces section, we locate the conversation ID associated with this interaction. Drilling into the trace reveals that the agent indeed made a call to the Web Search plugin. The trace shows an attribute with the type set to web_search_call, confirming that the tool was invoked.

The trace also reveals the query sent to the web search operation:
“Latest advancements in renewable energy 2025.”

This query was derived directly from the user’s original input. The web search plugin executes a search operation using this query and returns results to the agent.

Inspecting the response payload, we can see the structure of messages returned by the web search plugin. Within the content array, there is a notations array containing URL citations. Each citation includes a URL and a title, such as “Four Key Trends to Watch in Clean Energy Technology in 2025.”

The agent aggregates information from these URLs and synthesizes a coherent response for the user. The trace also shows the user input, the agent output, and metadata about token usage.

In total, this interaction consumed 7,254 tokens, reflecting the cost of web search grounding, document ingestion, and response generation.

This concludes the lab. We successfully built a Web Search Agent using the Foundry SDK in a code-first environment, observed autonomous tool invocation, validated grounding sources, and explored the trace stack to understand how the agent analyzed intent, called the web search plugin, and generated the final response.

# **D) Lab: Creating a Code Interpreter Agent (Hands-On Lab)**

In this video, we’ll take a look at the Code Interpreter capability that you can provide to your agent in the Microsoft Foundry ecosystem, using a code-first approach with the Foundry SDK.

To perform this lab, we navigate to the code-interpreter folder inside the agent-service directory. This folder contains three files. The first file is used for setting environment variables, which have already been configured with the Foundry project endpoint and the model deployment name. The second file is a Python notebook that contains the main codebase for this lab. The third file is a CSV file named electronics_products.csv, which contains product-related data such as product ID, product name, price, and color. This CSV file will be used as input data for the code interpreter analysis in this lab.

The overall flow of the lab is as follows. First, we upload the CSV file as a data asset to the Microsoft Foundry project through portal.azure.com. Next, we create a code interpreter agent and grant it access to both the code interpreter tool and the uploaded electronics_products.csv file.

When a user query comes in—such as “Create a column chart with products on the x-axis and prices on the y-axis”—the query is sent to the Foundry agent. The agent analyzes the intent, evaluates the available tools, identifies that it has access to the code interpreter tool and the CSV file, generates Python code using libraries such as Matplotlib, executes that code in a sandboxed environment, and finally returns the generated image as output. The result is a column chart with products on the x-axis and prices on the y-axis.

The first step is loading the environment variables from the .env file, which includes the Foundry project endpoint and the model deployment name. Once that’s done, we create a Foundry Project Client to establish a connection between the codebase and the Foundry ecosystem.

Since we are using GPT-4, which is an OpenAI model, we need to create an OpenAI client. This client is required to send queries to the agent and retrieve responses using the Responses API or Chat Completions API. The OpenAI client is created using the Foundry project client initialized earlier.

Next, we upload the electronics_products.csv file. To use the code interpreter with a file, the file must first be uploaded to the Foundry project, not directly to the agent. We use the OpenAI client’s files.create method with the purpose set to assistants, since the file will be used by the agent for code execution. The file is opened in read mode and uploaded, after which we receive a file ID. This file ID is crucial because it will later be provided to the agent so it can access the file during execution.

Once the file is uploaded and the file ID is obtained, we proceed to create the Code Interpreter Agent. Using project_client.agents.create_version, we create the first version of the agent. The model deployment name is set to GPT-4, and the system prompt instructs the agent that it is a helpful assistant with code interpreter capabilities.

In the tools definition, we add the Code Interpreter tool and pass the uploaded file ID inside a container of type code_interpreter_tool_auto. This configuration ensures that whenever the agent invokes the code interpreter, it automatically has access to the uploaded CSV file. This allows the agent to perform computations or visualizations directly on the dataset.

After the agent is created, we receive the agent ID, the agent name, and the version number, which is version one in this case.

Next, we create a conversation object to store the chat history between the user and the agent. This conversation object enables context retention and allows the agent to track interactions using a proprietary conversation ID.

Now we invoke the agent using the OpenAI client’s responses.create method. The user query is:
“Could you please create a column chart with products on the x-axis and the respective prices on the y-axis?”

At this stage, we do not print the textual response output. Printing response.output_text would only give a summary message from the agent, such as stating that the chart was created. However, the actual chart is generated as an image file (PNG) and saved as part of the Foundry project. The key task here is to programmatically retrieve that image.

To do this, we store the response ID returned by the agent. We then inspect the response object to check whether it contains a file citation. If a file citation exists, we extract the file ID, file name, and container ID associated with the generated image.

Using these values, we access the container, download the file in read mode, and save it locally within the project directory. Once downloaded, the image file is available as a column chart showing products on the x-axis and prices on the y-axis—exactly what we intended the agent to create.

Next, we inspect what code the agent actually executed in the sandbox environment. To do this, we go to the Foundry Portal, navigate to the Agents section, and select the Code Interpreter Agent. From there, we open the Traces section and drill down into the trace associated with the conversation ID.

Inside the trace, we can see that the agent invoked the Code Interpreter tool. The trace shows the Python code executed in the sandbox. Initially, the agent imports the pandas library and reads the CSV file to understand its structure. It inspects the first few rows to identify relevant columns.

In the next step, the agent reasons about the dataset internally, identifying the product name and price columns as relevant for creating the chart. This internal reasoning is recorded as part of the conversation history under the same conversation ID.

Finally, the agent executes the final block of code using Matplotlib to generate the column chart. Once completed, it responds with a message indicating that the chart has been created and asks if any modifications are needed. The generated image is referenced in the response annotations, which include the container ID, file ID, and file name.

We then programmatically retrieve this image using those identifiers, just as demonstrated earlier.

If we navigate to the Data section under the Foundry project, we can see all uploaded datasets. This includes the original electronics_products.csv file as well as any other files used by agents, such as PDFs uploaded for file search in previous labs. Every file used by an agent—whether for code interpreter or file search—must first be uploaded as a dataset to the Foundry project.

Behind the scenes, the workflow is consistent: upload the file, retrieve the file ID, and provide that file ID to the agent during creation so it can access the file when needed.

That concludes this video. We successfully demonstrated how to build and use a Code Interpreter Agent in Microsoft Foundry using a code-first approach, including file uploads, sandboxed code execution, trace inspection, and programmatic retrieval of generated artifacts.

# **E) Lab: Creating Agent with OpenAPI Tool (Hands-On Lab)**

In this video, we will be performing a lab where we create an agent using the Foundry SDK and supply it with an OpenAPI tool. For this lab, we are working inside the OpenAPI tool folder, which contains three files. The first file is the environment variables file (.env), the second is a Jupyter notebook, and the third is a file that contains the OpenAPI definition of the API we will be supplying to our agent, written in JSON format. All of these files are located under the agent service folder, which you can see in the project structure.

If you look at the .env file, it is already populated with the Foundry project endpoint and the model deployment name. For this lab, we will be using the OpenAI GPT-4 model to build the agent itself.

Now, coming to the lab flow, it works as follows. The weather_openapi.json file contains an OpenAPI definition of a free-to-use weather API, which can be accessed using the URL wttr.in. We will also take a look at how this API behaves. This OpenAPI definition includes details about all the available paths, parameters, GET and POST requests, and descriptions of how the responses from these requests will look. This information enables our agent to decide which endpoint to call, what query parameters to use, and what kind of response to expect.

When a user query such as “Tell me about London’s weather” comes in, the request goes to the Foundry agent. The agent understands that the user is asking for real-time information, which can be accessed either via a web search, an OpenAPI tool, or some external connection. Since the agent has access to an OpenAPI weather tool, it looks at the OpenAPI specification provided to it. Based on that definition, it decides which API endpoint to call, which query parameters to include, and how to handle authentication if required.

In this case, the API is unauthenticated and free to use, so we do not need to configure any authentication for the agent. However, if authentication such as JWT or OAuth were required, that could also be handled within the OpenAPI specification.

Let’s now take a closer look at the OpenAPI definition itself. The specification uses OpenAPI version 3.1.0. The title of the API is “Get Weather Data”, and the description states that it retrieves current weather data for a location based on wttr.in. Both the title and description are extremely important because when the agent is deciding which tool to use, it evaluates these fields to determine whether the tool is relevant to the user’s query. Better-defined titles and descriptions result in better agent behavior.

The API is hosted on a backend server URL pointing to wttr.in. Under the paths section, the API defines a /location endpoint that supports a GET request. This endpoint retrieves weather information for a specific location. The description of this endpoint is important because the agent uses it to decide whether this path should be invoked for the user’s request. The operation ID for this endpoint is getCurrentWeather, which is essentially a naming convention.

This endpoint accepts query parameters, including a location parameter. The description specifies that this parameter should contain the city or location for which weather data is required. It is a string parameter and is passed as part of the query string. The API can return a 200 status code for a successful response, which will be a string containing the weather data. A 404 status code indicates a client-side error, such as an incorrect or unknown location.

To demonstrate how the API works, we can manually call it. If we navigate to wttr.in/London?format=j1, we receive a JSON response. The response is fairly large and includes details such as the current temperature in both Celsius and Fahrenheit, cloud cover, humidity, precipitation, pressure, UV index, visibility, and a textual weather description (for example, “partly cloudy”).

With that understanding, we proceed to the lab implementation. First, we set up the environment variables by loading the Foundry project endpoint and model deployment name from the .env file. Next, we initialize the Foundry project client, which allows our codebase to connect to the Foundry project.

We then initialize the OpenAPI tool. This involves opening the file that contains the OpenAPI definition, reading it into a variable (for example, openapi_weather), and then using it to create an OpenAPI tool. The tool type is set to openapi, the name is set to weather, the specification is the OpenAPI JSON we just read, and the authentication type is set to anonymous.

After that, we create the agent itself. The agent is named Weather Agent, and we create version 1 using project_client.agents.create. In the agent definition, we provide instructions stating that the agent should help users by providing weather information using the supplied OpenAPI tool. The weather tool is then appended to the agent’s tools array. Once the agent is created, we receive an agent ID in return.

Next, we create an OpenAPI client to interact with the agent and also generate a conversation ID to maintain conversational context. We then ask the agent a question: “What’s the weather like in New York City today?” This query is sent to the agent using the OpenAI client, passing in the conversation ID, agent reference, and the user input.

After running the cell, the agent responds with detailed weather information for New York City. It reports the current temperature as 2°C, feels-like temperature as -2°C, weather condition as freezing fog, humidity at 51%, wind coming from the west-southwest at 17 km/h, and visibility of 10 km. It also provides a forecast showing a high of 4°C, a low of -3°C, UV index of 0, sunrise at 7:40 a.m., and sunset at 4:28 p.m.

To verify the correctness of the response, we manually query the API using wttr.in/New York?format=j1. The values returned by the API—such as feels-like temperature, UV index, wind direction, and wind speed—exactly match the information provided by the agent, confirming that the agent is correctly consuming the API response.

Finally, if we navigate to the Foundry portal, we can see the newly created agent. In the tools section, the OpenAPI definition is visible. In the traces section, selecting the conversation ID shows the full trace of the interaction. We can see that the agent invoked a remote function call corresponding to the getCurrentWeather operation, passing location=New York City and format=j1 as arguments.

Although the API response itself is not fully visible in the trace—likely because it was large and truncated—we can still see the final message generated by the agent. The metadata section reveals that 11,026 tokens were used during this interaction. Despite the user query and response being relatively small, the token usage is high because the agent processed the entire API response, which significantly increases token consumption.

This highlights an important consideration when using OpenAPI tools: large API responses can inflate token usage, making cost estimation challenging. Controlling or optimizing this behavior remains a gray area and is something to watch out for. Nonetheless, this lab successfully demonstrates how to create an agent using an OpenAPI tool definition.

With that, we conclude the lab on creating an agent with an OpenAPI tool, and we can now move on to the next set of videos.

# **F) Lab: Creating a MCP Server Agent (Hands-On Lab)**

With this lab, we will explore how to integrate an MCP (Model Context Protocol) server—specifically an already existing MCP server—into a Foundry agent, so that the MCP server can act either as a tool or as a knowledge retrieval source for the agent.

For this lab, we are working inside the MCP server folder, which is located within the Agent Service parent folder. Inside the MCP server folder, there are two files. The first file is the environment variables file (.env), and the second file is a Jupyter notebook that contains the entire codebase for the lab.

Let’s first understand the overall flow of the lab. There is an MCP server that has already been published by the Microsoft Learn team. This MCP server provides access to all Microsoft Learn documentation, code examples, and learning modules available on learn.microsoft.com. Essentially, the entire Microsoft Learn ecosystem is exposed through this MCP server.

We will take this publicly accessible MCP server, grab its URL, and integrate it with our Foundry agent. This MCP server is unauthenticated, meaning it allows anonymous access and is completely free to use. Once connected, the agent can use this MCP server to retrieve information whenever a user query comes in.

For example, if a user asks, “Find me learning paths on Azure AI services for building intelligent applications”, the query is sent to the agent. The agent then looks at the connected MCP server, lists all the tools exposed by that MCP server, and invokes the appropriate tool to retrieve the required information. The retrieved data is then used by the agent to generate an accurate response for the user.

Now, looking at the .env file, the Foundry project endpoint and model deployment name are already configured. However, one value is still missing—the MCP server name. To fill this in, we must first register the MCP server in the Foundry portal. Any MCP server—whether custom-built or provided by a verified vendor like Microsoft—must be registered in the Foundry portal to enable governance, observability, and compliance.

To do this, we navigate to the Foundry portal, go to the Build section, and then move to the Tools area, which is where agent tools are managed. From there, we select Connect Tool, choose Custom, and then select Model Context Protocol Server. Clicking on Create brings up the configuration screen.

We then provide the tool details. The name is set to MS Learn MCP Server. Next, we specify the remote MCP server endpoint. To confirm the correct endpoint, we search for “Microsoft Learn MCP server” and find the official URL, which is learn.microsoft.com/api/mcp.

Since this MCP server is unauthenticated, we select the Unauthenticated option. If this were a protected MCP server, we could configure authentication using API keys, Microsoft Entra ID, or OAuth identity passthrough. After selecting the unauthenticated option, we click Connect, which registers the MCP server in the Foundry environment.

Once registration is complete, the MCP server appears in the Tools section of the Foundry portal. We then copy the registered MCP server name and paste it into the .env file under the MCP server name field. At this point, the environment setup is complete.

Next, we execute the codebase. The first step is loading the environment variables and storing them as Python variables—namely, the Foundry project endpoint, model deployment name, and MCP server name. It is critical that the MCP server name exactly matches the name registered in the Foundry portal, otherwise the integration will fail.

We then initialize the Foundry project client using the project endpoint and default Azure credentials. Alongside this, we also initialize the OpenAI client, which will later be used to invoke the agent built on the GPT-4 model.

To connect the MCP server to the agent, we need something called a connection ID. Every tool registered in the Foundry portal is assigned a unique connection ID. This ID is used to grant the agent access to that tool.

The notebook retrieves the connection ID by calling project_client.connections.list(). It iterates through the available connections and compares the connection name with the MCP server name stored in the environment variables. When a match is found, the corresponding connection ID is stored in a variable.

The MCP server connection ID follows a specific structure. It includes the subscription or tenant identifier, resource group name, project name, and finally the connection name (for example, /connections/ms-learn-mcp-server). This structure applies to MCP servers as well as other tool connections.

With the connection ID available, we create the MCP tool specification. This includes a server label (used as an identifier), the MCP server URL (learn.microsoft.com/api/mcp), and a parameter called require_approval, which is set to never. By default, this value is set to always, which would require manual approval for every MCP call. Since we are working in a code-first environment, we disable approval to avoid unnecessary complexity.

The final parameter in the MCP tool specification is the project connection ID, which is set to the MCP server connection ID we retrieved earlier. With this, the MCP tool is fully configured.

Next, we create the agent itself. The agent is named MCP Agent, uses the GPT-4 deployment, and has instructions stating that it is an intelligent assistant capable of interacting with the Microsoft Learn MCP server. The MCP tool specification is added to the agent’s tools array. Once created, the agent is ready for use.

We then create a conversation object to maintain contextual history between the user and the agent. Using this conversation ID, we submit the first user query: “Can you help me with the latest AI Foundry SDK code sample?”

The agent responds with relevant code samples and provides official Microsoft Learn links. When we click one of these links, it opens the corresponding learn.microsoft.com documentation page, confirming that the MCP server integration is working correctly. This experience feels like a powerful, natural-language-driven search engine over Microsoft Learn.

We then try another query: “Find me learning paths on Azure AI services for building intelligent applications.” The agent responds with multiple learning paths, including Get started with Azure AI, Develop generative AI apps in Azure, Develop natural language solutions in Azure, and Develop AI agents on Azure. Some of these learning paths include several modules and hours of content.

To understand how this works internally, we examine the trace logs in the Foundry portal. For the first query, the agent first asks the MCP server to list all available tools. The MCP server responds with tools such as Microsoft Docs Search and Microsoft Code Sample Search.

Since the first query was about code samples, the agent correctly invoked the Microsoft Code Sample Search tool. For the second query related to learning paths, the agent invoked the Microsoft Docs Search tool. In some cases, the agent invokes multiple tools to gather additional context before responding.

Looking at token usage, the first query consumed approximately 8,382 tokens, while the second query used around 17,179 tokens. This high token usage occurs because the agent processes large amounts of information returned from Microsoft Learn, and also includes context from earlier conversation runs.

In summary, this lab demonstrates MCP in action by integrating a public, unauthenticated Microsoft Learn MCP server with a Foundry agent. The agent can dynamically retrieve documentation, code samples, and learning paths using natural language queries. This concludes the lab on creating an agent with a remote MCP server, and with that, we can move on to the next set of videos.

# **G) Creating a Multi-Tool Agent (Hands-On Lab)**

In this video, we explore how multi-tool capability works in a Foundry agent. Until now, we have been working with tools in isolation, where each agent was created with only a single tool. What we want to understand now is what happens when an agent is provided with multiple tools. Specifically, we want to see whether the agent can understand the intent of a user query and dynamically derive an execution plan that routes different parts of the request to the appropriate tools.

The goal is to observe whether the agent has an internal orchestration mechanism that decides which tool to use, in what order, and whether it should use one tool, multiple tools sequentially, or only a subset of the available tools depending on the user query. This is the key focus of the lab.

To perform this lab, we work inside the multi-tool folder, which is located within the Agent Service parent folder. This folder contains three files: one file for setting environment variables, a second file containing the main codebase, and a third file that includes the OpenAPI definition of a weather API.

In this lab, we aim to create a Foundry agent that has access to two tools. The first tool is the Microsoft Learn MCP server, and the second tool is the OpenAPI-based weather API that we explored in an earlier video. The same applies to the MCP server—if you have not already gone through the MCP server lab, it is recommended to review that video before proceeding.

Once the agent is created with both tools, consider a user query such as: “Let me know the weather in Seattle and also find me a Microsoft Learn module on Microsoft Foundry.” When this query reaches the agent, the agent should split the intent. For the first part, it should invoke the OpenAPI weather tool with the location set to Seattle. For the second part, it should invoke a tool from the Microsoft Learn MCP server to search for relevant Microsoft Foundry learning modules on learn.microsoft.com.

This allows us to observe the agent’s execution rollout and experience its internal orchestration capabilities. The agent dynamically determines which tools to invoke and how to combine their outputs into a single coherent response.

Moving on to the environment variable file, the values for the Foundry project endpoint, model deployment name, and MCP server name are already filled in. The MCP server used here is the same one set up in the earlier MCP server lab. The remote MCP server endpoint is learn.microsoft.com/api/mcp, and it is an unauthenticated MCP server.

The OpenAPI definition included in this folder makes a call to the weather API using a single endpoint, /location, which retrieves weather information for a specified location. Once the environment variables are verified and saved, we are ready to proceed with the lab.

The first step in the code is to load the environment variables from the .env file and store them as Python variables, including the Foundry project endpoint, model deployment name, and MCP server name. Next, we create a Foundry project client, which connects the codebase to the Foundry project resource.

After that, we initialize an OpenAI client, which will be used later to invoke the agent. We then move on to initializing the OpenAPI weather tool. This involves reading the OpenAPI specification JSON file, storing it as a Python variable, and creating the tool with its type set to openapi, name set to weather, and specification pointing to the loaded JSON content.

Next, we need to initialize the MCP server connection. To do this, we list all the connections available in the Foundry project using the project client. When the connection name matches the MCP server name from the environment variables, we identify it as the correct MCP server and store its connection ID in a Python variable.

With the connection ID available, we create the MCP tool specification. The server label is set to a descriptive name, the server URL is set to the MCP server’s remote endpoint, and the require_approval parameter is set to never so that the agent can autonomously execute MCP calls. The project connection ID is set to the MCP server connection ID obtained earlier.

At this point, we create the agent with multiple tools. The agent is named Multi Tool Agent, and it is created using project_client.agents.create. The agent instructions specify that it is a helpful assistant capable of using multiple tools to answer user queries. In the tools array, we pass both the weather OpenAPI tool and the MCP tool, demonstrating how multiple tools are encapsulated within a single agent definition.

Once the agent is created, we create a conversation object to maintain contextual conversation history between the user and the agent. We then invoke the agent with the user query: “Let me know the weather in Seattle and also find me a Microsoft Learn module on Microsoft Foundry.”

For the first part of the query, the agent calls the weather API and returns the current weather in Seattle. The response indicates a temperature of 7°C, including both the actual and feels-like values. The weather condition is overcast, humidity is 82%, wind speed is 2 miles per hour from the south, pressure is 1028 pascals, visibility is 16 kilometers, and the UV index is set to zero.

For the second part of the query, the agent retrieves information from the Microsoft Learn MCP server. It suggests a module titled “What is Microsoft Foundry”, provides highlights from the module, and includes links to the relevant Microsoft Learn content. This confirms that the agent successfully combined outputs from both tools into a single response.

To understand how this worked internally, we navigate to the Foundry portal and inspect the trace stack. In the agent’s configuration, we can see that two tools are attached. In the traces view, we analyze the conversation ID associated with this run.

The trace shows that the total token usage is around 17,000 tokens. First, the agent makes a call to the MCP server to retrieve the list of available tools. Then it invokes the Microsoft Docs Search tool to fetch learning modules from Microsoft Learn. Finally, it makes a remote function call to the OpenAPI weather tool to retrieve weather information for Seattle.

In total, two function calls are made—one to the MCP server and one to the OpenAPI weather API. These calls are clearly visible in the trace stack, confirming the agent’s ability to orchestrate multiple tools dynamically.

This concludes the demonstration of a multi-tool agent in action. With that, we wrap up this lab and move on to the next set of videos.

# **H) Lab: Working with Browser Automation Tool (Hands-On Lab)**

In this video, we work with the Browser Automation tool in a Microsoft Foundry agent. To perform this lab, we use the automation.ipynb Jupyter notebook. This notebook is located inside the browser automation folder, which itself resides within the agent service folder.

Before executing any code in this notebook, we first need to configure a few required environment variables. These include the Foundry project endpoint, the model deployment name, and a value called the browser automation connection name. In order to use the browser automation tool inside our notebook, we must first create a corresponding browser automation connection in the Microsoft Foundry portal.

To do that, we navigate to Portal.azure.com. The first thing we need to deploy is something called a Playwright Workspace in Azure. We search for Playwright Workspace in the Azure portal and select it. The reason we deploy this resource is because browser automation inside a Foundry agent relies on Playwright to simulate real browser interactions. This allows the agent to behave like a human user—opening a browser, clicking buttons, navigating pages, and extracting information.

If we want to automate the process of navigating through a browser UI and retrieving information, the agent needs a sandboxed browser environment. The Playwright Workspace provides exactly that. It allows the agent to navigate through web pages, interact with UI elements based on instructions, and return the extracted information after completing those steps.

Deploying a Playwright Workspace is straightforward. You simply click Create, choose a resource group, provide a workspace name, and proceed. A free trial is started automatically, which typically lasts around 14 days. Once the trial expires, the resource switches to a pay-as-you-go billing model. Importantly, you are billed only when the agent actively uses the Playwright Workspace. Pricing details can be reviewed using the Azure Pricing Calculator.

In addition to browser automation, Playwright Workspaces are commonly used for automated software testing. For example, they can be used to test web applications or mobile apps by simulating UI interactions. This is an industry-standard use case documented in the Playwright Workspace documentation.

Once the Playwright Workspace is deployed, navigating to its Overview section shows two important values: the API base endpoint and the browser endpoint. The browser endpoint is the one required to establish a connection between the Foundry agent and the browser automation tool.

Next, we return to the Microsoft Foundry project. From there, we go to the Build section, and then to Tools, which is located just below the fine-tuning option. Here, we click on Connect Tool and select the browser automation tool from the configured tools list. We then click Add Tool.

At this stage, we are prompted to provide a connection name. We create a new connection and name it Browser Automation Udemy Demo. This connection name is copied and stored in the environment variable file as the browser automation connection name.

We then need to provide the Playwright Workspace browser endpoint, which we copy from the Playwright Workspace overview page. Additionally, the agent requires an access token to authenticate with the Playwright Workspace. To generate this, we go to Access Management under the Playwright Workspace settings and choose Playwright Service Access Token. We generate a new token, name it Udemy Demo Token, set an expiration period (for example, seven days), and generate it.

The generated token is visible only once, so it must be copied immediately and stored securely. We paste this token into the access token field and click Connect, which completes the setup of the browser automation tool inside the Microsoft Foundry project.

With the browser automation connection successfully created, we then return to the Foundry project home page. From there, we copy the project endpoint and update it in the environment variable file. We also specify the model deployment name, which in this case is a GPT-4 model that has already been deployed. After saving these changes, we are ready to run the notebook.

We select the Python kernel in Jupyter and begin executing the notebook. The first step loads the environment variables, including the project endpoint, model deployment name, and browser automation connection name. Next, we create a Foundry project client using the project endpoint and Azure CLI credentials.

After that, we create an OpenAI client, which is used to create a conversation and retrieve a conversation ID. This conversation ID is essential for maintaining the chat context between the user and the agent.

Using the browser automation connection name, we iterate through all the connections available in the Foundry project by calling project_client.connections.list(). When the connection name matches the browser automation connection name defined in the environment variables, we store its connection ID in a Python variable. This confirms that we have successfully retrieved the browser automation tool connection ID.

Next, we create a browser automation tool specification using this connection ID. From this specification, we construct a browser automation agent tool object, which will later be attached to our agent.

We then create the agent itself. The agent is named Browser Automation Agent, uses the GPT-4 model, and is configured with the browser automation tool we created earlier. The agent’s instructions define it as a helpful assistant capable of automating web browser tasks using the browser automation tool.

After that, we create a conversation object using the OpenAI client and retrieve the conversation ID. This conversation ID is used both for executing the agent and for later inspecting the agent’s execution stack in the Foundry portal.

Next, we call the agent with a user query. When using browser automation, it is extremely important to be very specific in the instructions provided to the agent. The user query instructs the agent to report the year-to-date percentage change in Microsoft’s stock price. It explicitly describes each UI interaction step: navigating to finance.yahoo.com, using the search bar to search for Microsoft, clicking the YTD option on the stock chart, and extracting the percentage value displayed below it.

This level of detail is critical when working with browser automation tools. Without precise instructions, the agent’s behavior may become unpredictable, leading to errors and a poor user experience. Controlling agent behavior is one of the biggest challenges developers face when building agentic systems.

Once the query is submitted, the agent executes successfully. In the Microsoft Foundry portal, we can navigate to the agent, select the corresponding conversation ID, and view the execution trace. The agent initially failed on the first attempt, but succeeded when executed a second time. Execution latency is noticeable, often taking two to three minutes, which is an important consideration when designing workflows.

Because of this latency, browser automation is best suited for long-running or background tasks that do not require immediate human interaction. In this case, the agent reports that the year-to-date percentage change for Microsoft stock, as shown on Yahoo Finance, is 14.3%.

Looking at the agent execution stack, we can see that the agent analyzed the user query, invoked the browser automation tool, synthesized the response from the tool, and finally returned the result to the user.

Additional queries were also tested. For example, asking the agent to search for Microsoft Foundry courses on Udemy. Although the browser automation tool was invoked, the agent encountered Cloudflare and CAPTCHA restrictions, preventing access to the search results. This highlights an important limitation: not all websites allow automated or bot-based access, especially sites protected by Cloudflare or CAPTCHA mechanisms.

When building browser automation agents, it is essential to choose target websites that allow agentic access and browser automation. Otherwise, such restrictions can prevent successful execution.

With that, this concludes the video demonstration of using the Browser Automation Tool with a Microsoft Foundry Agent. In the next set of videos, we move on to additional concepts and scenarios.

# **I) Introduction to Foundry Memory Store**

Let’s now talk about one of the latest additions in Microsoft Foundry, which revolves around Memories and the memory store used in the agents that you build.

To begin with, let’s understand the problem statement that led to the introduction of this feature. After speaking with many developers and reviewing multiple discussion forum threads, a common challenge emerged. Organizations and developers faced significant difficulties when building AI agents and pushing them to production, mainly due to the complexity of implementing a contextual memory store.

Traditionally, developers had to set up external databases, such as NoSQL databases or external vector databases, to maintain agent memory. Every time a user session timed out, retrieving the contextual memory became complicated. Developers had to make multiple API calls to backend databases to reconstruct the context. This process was not only cumbersome but also inefficient.

Another major issue was deciding how much memory should be retrieved and injected back into the agent’s context. Including the entire memory store in a new prompt is unnecessary and inefficient. Doing so significantly increases token usage, leading to higher costs and frequent encounters with token limits and rate restrictions. Hence, a more intelligent and token-efficient solution was required.

These challenges collectively led to the advent of Memories in Microsoft Foundry. Earlier, retrieving agentic context across user sessions was a major headache. A built-in solution similar to Microsoft 365 Copilot’s memory system would clearly be beneficial.

To relate this to a real-world example, consider Microsoft 365 Copilot. With an active Copilot license, if you navigate to the Copilot web experience and open the Settings page, you’ll find a Personalization tab. Within this tab, there is an option to enable or toggle Copilot Memory. When this feature is enabled, Copilot remembers important details from past conversations—even from weeks or months ago.

This naturally raises the question: Can we implement a similar memory system in the AI agents we build?
The answer is yes, and that’s exactly what the memory store in Microsoft Foundry solves.

One of the most important things to understand is that you do not need to set up any external database to implement this memory store. Everything comes built-in—including vectorization logic, embedding generation, and retrieval mechanisms. From a developer’s perspective, all you need to do through code is handle how user input is sent to the memory store and how relevant memories are retrieved when needed.

Additionally, within the Foundry portal, this feature can be enabled using a simple toggle button, making setup extremely straightforward.

Conceptually, you can think of the memory store in Microsoft Foundry as a vector database that persists memory across user sessions. Let’s walk through an example to understand how this works.

Suppose a user sends the following query to the agent:
“I’m allergic to dairy. Show me a recipe for cake.”

Here, the user expects the agent to remember a personal attribute—being allergic to dairy or lactose intolerant. This query is sent to the agent, but it is also processed by the memory store, which contains an LLM-powered component.

This large language model within the memory store analyzes the incoming query and intelligently identifies what information is worth storing. Importantly, the entire user query is not stored. Instead, the LLM selectively extracts only the relevant, long-term memory-worthy information—in this case, “allergic to dairy.” This approach ensures that the memory store remains token-efficient.

Even though the original query may be large, only a concise, meaningful statement is stored in memory.

Now, imagine that a few weeks later, the same user returns and asks:
“What are some good snacks for my party tomorrow?”

In this query, the user does not explicitly mention their dairy allergy. However, because this information already exists in the memory store, the agent retrieves it and factors it into the response. As a result, the agent suggests dairy-free snacks, providing a more personalized and context-aware answer.

So how does this retrieval mechanism actually work?

Each memory stored consists of two components:

Textual content (e.g., “allergic to dairy”)

Vector embedding of that content

When a new user query comes in, vector embeddings are generated for the query as well. These embeddings are then compared against the embeddings stored in the memory store using similarity search. Based on configuration, the system retrieves the top-K most relevant memory chunks—for example, the top 3 or top 5.

These retrieved memory chunks are then appended to the final prompt sent to the agent. They serve as grounding context, enabling the agent to take personal user attributes into account when generating a response.

Microsoft published a study on this approach, which included two industry-standard tests (referred to as Test 1 and Test 2). The results showed that when memory stores were used, accuracy increased by approximately three times.

The study also compared results using GPT-4.1 Mini and GPT-4.1. While both models showed improved accuracy with memory enabled, GPT-4.1 performed significantly better. The key takeaway here is that larger reasoning models benefit more from memory stores. Better reasoning capabilities allow the model to more accurately determine which topics should be stored and retrieved, leading to higher overall accuracy.

Finally, let’s discuss the current limitations and quotas of the memory store, as of 12th December 2025.

At present, memory stores work only with Azure OpenAI models. Additionally, you must explicitly set a scope value. The scope value acts like a unique identifier—similar to a primary key in a database. For example, if you are storing user-specific memories, the scope could be the user’s name or user ID. Each scope represents an independent memory store.

Since the feature is currently in preview, the following limits apply:

Maximum number of scopes per memory store: 100

Maximum memories per scope: 10,000

Memory search (retrieval) limit: 1,000 requests per minute

Memory update (write) limit: 1,000 requests per minute

These quotas are critical to consider when designing solutions that need to scale.

In summary, memory stores in Microsoft Foundry are one of the most advanced and much-needed additions to the ecosystem. They eliminate the need for external databases, simplify contextual memory management, improve personalization, and significantly enhance agent accuracy.

With that, we’ve covered everything about memory stores in Microsoft Foundry.
Without further ado, let’s move on to the next set of videos.

# **J) Lab: Assigning Azure Rule to Foundry for Memory Store Lab (Hands-On Lab)**

Before we begin with the Foundry Memory Store lab, there are a few mandatory administrative steps that need to be completed in portal.azure.com.

Whenever you create a Foundry Memory Store, the identity of your Foundry project must be granted the Azure AI User role on the parent resource in the Azure portal. This step is critical for the memory store to function correctly.

The reason for this requirement is that the Foundry Memory Store has two core components. The first component is a large language model, which is responsible for identifying and extracting the relevant topics from user queries that should be stored as memories. The second component is the embedding model, which generates vector embeddings for those topics so they can be stored and retrieved efficiently from the memory store.

For your Foundry project—and the Foundry client that you will create via code—to access these OpenAI models (both the large language model and the embedding model), the project’s managed identity must have the Azure AI User role. This role needs to be assigned at the level of the resource that hosts the OpenAI models, which typically means the resource group containing the AI service account in the backend.

Granting this role ensures that the Foundry project has permission to interact with both the LLM and embedding models. Without this role assignment, the memory store will not be able to function correctly.

To begin, navigate to portal.azure.com and search for Microsoft Foundry in the search bar. Once selected, you will land on the Foundry overview page.

From here, you need to determine which AI service account hosts the project for which you intend to create the memory store. To do this, open the Foundry portal, select the project you are currently working on, and then click on View all projects.

Once inside the project details, you will see information indicating the parent resource associated with the project. In this example, the parent resource is named something like carbon-ops-dev-ai followed by numeric characters. This parent resource is what hosts the OpenAI models.

The next step is to assign the Azure AI User role to the managed identity that was automatically created for this Foundry project, and to assign it on top of the parent resource. This ensures that the project can access the OpenAI and embedding models hosted by that resource.

Now, return to the Foundry view in portal.azure.com and select the identified parent resource. From there, navigate to the Projects section, where you will see the demo project that you are working with.

Click on the project to open the project pane. Inside the project pane, go to Resource Management, and then select Identity. This is where you configure roles and administrative permissions for the project.

You will notice that the project already has a system-assigned managed identity. This identity is automatically created by Azure when a Foundry project is created within a parent resource. The Object ID or Principal ID shown here uniquely identifies this managed identity.

Next, click on Azure Role Assignments, as we want to attach a new role to this identity. You may already see the Azure AI User role assigned if it was previously configured for testing, but the process remains the same.

Since both the Foundry project and the parent AI resource reside in the same resource group, assigning the Azure AI User role at the resource group level is sufficient. Doing so automatically grants the project access to the parent resource.

To add the role, click on Add Role Assignment. Set the Scope to Resource Group, and then select the resource group where both the Foundry project and the parent AI resource exist. In this case, the resource group is carbon-ops-dev.

Next, select the Role by searching for Azure AI User. Once you locate the role, select it and click Save.

This action assigns the Azure AI User role to the project’s managed identity at the resource group level. As a result, the Foundry project now has permission to access the OpenAI models hosted within the parent resource.

Once this configuration is complete, you will be able to successfully run the Foundry Memory Store lab. If this step is skipped, you will encounter unauthenticated or authorization errors when executing the code. This is a common bottleneck and one of the most frequent causes of issues when setting up memory stores.

That’s all for this section.
With the administrative setup complete, let’s move on to the next set of videos.

# **K) Lab: Working with Foundry Memory Store (Hands-On Lab)**

Alright, in this video we’ll be working hands-on with the Foundry Memory Store. To perform this lab, I’m using the memory_store.ipynb Python notebook. This notebook is located inside the memories folder, which itself resides under the Agent Service parent folder.

Before running the notebook, the first thing we need to do is review and set the required environment variables. We need to configure the Foundry project endpoint, along with the model deployment name and the embedding model name. I’ve already set these values in my .env file.

For this lab, I’m using the GPT-4.1 model as the language model and text-embedding-3-small as the embedding model. If you haven’t deployed these models yet, you can do so from the AI Foundry portal. Simply navigate to the Models section, click on Deploy a base model, search for GPT-4.1, and deploy it using the default settings. Then repeat the same process for text-embedding-3-small, again using default values.

Once deployed, you’ll be able to see both models listed in the portal—GPT-4.1 for reasoning and text-embedding-3-small for embeddings. With that setup complete, we’re ready to begin working with the notebook.

The first step in the notebook is setting up the environment. We load the Foundry project endpoint, the model deployment name, and the embedding model name from the .env file. After that, we create the Foundry project client using the project endpoint along with the default Azure credential, which is picked up from the Azure CLI.

This is where the core work begins: defining the memory store. The Azure AI Projects SDK provides a built-in way to define memory stores using the memory store default definition and memory store default options objects.

As discussed earlier, the memory store has two major components. The first is the language model (LM) component, which uses its natural language processing capabilities to analyze incoming user queries and identify the most relevant topics or phrases that should be stored as memories. We intentionally avoid storing the entire user query, as that would lead to token exhaustion and could introduce unnecessary noise during memory retrieval.

In this lab, the LM component of the memory store is powered by GPT-4.1. If you’re using a different model, the one defined in your .env file will be used instead.

The second component is the embedding model, which is crucial because the memory store functions like a vector database. Each memory consists of both text and vector embeddings. These embeddings are later used during retrieval to identify the most relevant memory chunks that will form the grounding knowledge for the agent. In this case, the embedding model used is text-embedding-3-small.

In the memory store options, both user profile and chat summary are set to true. This allows the system to summarize conversations and store information in a more token-efficient manner.

Once the definition is ready, we use the Foundry project client to create the memory store. We name it “Udemy Demo MemoryStore v1” and provide a description stating that it is used to retain user context across sessions. The description is purely informational and intended for developers; it does not affect how the agent uses the memory store.

With that, the memory store is successfully created.

Next, we define a function to update the memory store. The idea is that during an ongoing chat loop, every time a user sends a message, this function will be invoked to update the memory store with any new relevant information.

This function takes three inputs:

The memory store name, to identify which store to update

The username, which is used as the scope

The user message, which is the incoming query or information

The scope works like a unique identifier in a database. Each user gets their own independent set of memories within the parent memory store.

Inside the function, we create an object of type ResponsesUserMessageItemParam, which is required to pass user input into the memory store. We then use the project client to begin the memory update operation, providing the memory store name, the scope (username), and the user message.

Since memory updates involve multiple steps—topic extraction by the LLM and embedding generation—we use a poller to wait for the operation to complete. Once finished, the function returns a success message. If any exception occurs, it returns an update-failed message.

To see this in action, we invoke the function with the scope set to “kujo” and provide the user message:
“My name is Kujo Singh. I love programming in Python. I’m also allergic to peanuts and dairy.”

As a result, the memory store is updated with multiple memory chunks. These include:

User’s name

User loves programming in Python

User is allergic to peanuts

User is allergic to dairy

A combined summary memory capturing these details

Each of these is stored as a separate chunk with its own memory ID under the specified scope.

Next, we move on to creating an agent in the Foundry Agent Service. Until now, we’ve only created the memory store and verified that memory updates work correctly. Now, we’ll bring everything together by creating an agent that actively uses the memory store as contextual grounding.

We create an agent named “Helpful Assistant Agent”, using the Foundry project client. This is version one of the agent. The agent is based on the GPT-4.1 model, with instructions to behave as a helpful assistant that responds in a friendly and informative manner.

After that, we build a chat system to demonstrate memory usage in real time. This part involves more plumbing code, so I’ll explain the logic at a high level.

The chat loop runs continuously until the user types exit. If the user types update, they are prompted to enter information they want the agent to remember. That input is then passed to the memory update function.

If the user simply asks a question, we first create an OpenAI client and request a conversation ID. Before sending the query to the agent, we perform a search operation on the memory store.

The user query is converted into a ResponsesUserMessageItemParam object, which is used to perform a retrieval operation. We call search_memories, passing the memory store name, the scope (username), the query item, and retrieval options.

The max_memories value is set to 5, meaning the top five most relevant memory chunks for that user and query will be retrieved. These memory chunks are appended to the final prompt as grounding context before sending the request to the agent.

Now let’s see this in action. The memory store already contains the facts that the user loves Python and is allergic to peanuts and dairy. When we ask, “Can you tell me some quick snack recipes?”, the agent retrieves the relevant memory chunks and responds with peanut-free and dairy-free snack ideas, even though those allergies were not explicitly mentioned in the question.

Similarly, when asked, “Give me code to calculate the factorial of a number in my favorite programming language,” the agent correctly responds with Python code, based on the stored memory that Python is the user’s preferred language.

Next, we update the memory again by adding:
“My favorite comic star is Batman.”

After the memory store updates, we ask, “Can you tell me some qualities about my favorite comic star?” The agent retrieves the stored memory and responds with a detailed list of Batman’s qualities.

Typing exit ends the chat loop.

Finally, we switch to the Foundry portal and navigate to the Agent section. Selecting the Helpful Assistant Agent, we open the Memories option and attach the Udemy Demo Memory Store directly to the agent. We enable memory access, set the scope, and save the agent, creating version two.

Now, when interacting with the agent directly—without any custom plumbing code—it can still recall personal details such as favorite comic star or allergies. This approach reduces code complexity but gives you less control over when memories are stored or retrieved, as those behaviors are abstracted away.

That’s the trade-off to consider.

And with that, we’ve seen the Foundry Memory Store fully in action, both programmatically and through the portal.
That wraps up this section—let’s move on to the next set of videos.

# **IV) Building an End-to-End RAG Agent**

# **A) What is RAG (Retrieval Augmented Generation) ?**

Now let's talk a bit about what RAG or Retrieval Augmented Generation is. RAG stands for Retrieval Augmented Generation, and it helps your generative AI chat engine answer queries from users or leverage proprietary enterprise knowledge whose information might not be in the AI’s existing database.

One of the key problems with large language models (LLMs) and AI agents is that integrating enterprise knowledge can be challenging. There are generally two approaches. The first approach is to create a custom model using the enterprise’s own training dataset. However, this is very costly and not financially practical, as it can require millions of dollars. The second challenge is a talent constraint — very few people have the expertise to build such large models from scratch.

So, how can you build a cost-effective and resource-efficient AI agent that can answer queries based on enterprise documents? The answer is RAG — Retrieval Augmented Generation.

The RAG architecture is composed of three main components: retrieval, augment, and generation.

The first component, retrieval, is responsible for fetching documents that best match the user query. Enterprises often have a large collection of unstructured data stored in a vector database. The retrieval function performs a similarity search, comparing the user query against the documents in the database to identify the most relevant ones for answering the query.

The second component, augment, takes the retrieved documents and uses them to create a new prompt. This prompt combines the user query with the content of the retrieved documents as grounding knowledge. This augmented prompt is then sent to the large language model.

The third component, generation, is where the large language model takes the augmented prompt — containing both the user query and the retrieved contextual information — and generates a response. This ensures that the AI’s answer is grounded in the enterprise knowledge stored in the documents.

To visualize this, imagine a couple of documents indexed in a vector database. Vector databases store both the text content of the documents and vector embeddings, which are numerical representations of the document content in a high-dimensional space. These vectors are not limited to 2D or 3D; they can span 1536, 3072, or even more dimensions, capturing the nuanced semantic meaning of the content.

Vector embeddings are generated by embedding engines such as text-embedding-002 or other large embedding models. These embeddings are then stored in a vector index to facilitate semantic similarity searches.

For example, if a user query is:
"How do you evaluate the fact that OpenAI CEO Sam Altman went through a certain dismissal by the board in just three days and was then rehired, resembling a real-life version of Game of Thrones in terms of power dynamics?"

The system computes vector embeddings for the user query and compares them to the embeddings of all stored documents. A similarity search retrieves the top 5–10 documents that best match the query — this is the retrieval step.

Next is the augment step. Here, a new prompt is created, combining the user query with the content of the retrieved documents. So, if three documents are retrieved, their content is appended to the query to form a single, augmented prompt.

Finally, the augmented prompt is sent to the large language model. The model uses both the query and the retrieved content to generate a response. This ensures the answer is deeply grounded in the actual documents stored in the vector database. Without this RAG pipeline, a model might respond generically, saying something like:
"I’m unable to provide comments on future events. Currently, I do not have information regarding the dismissal and rehiring of OpenAI's CEO."

Vector databases are not your traditional SQL databases. They are specifically designed to store both textual content and vector embeddings, enabling semantic search. Open-source options include ChromaDB or QuadrantDB, while in the Azure ecosystem, there is Azure AI Search, a vector database capable of supporting embeddings along with textual content.

Interestingly, ChatGPT’s backend likely uses Azure AI Search due to the partnership between OpenAI and Microsoft. Azure AI Search supports storing vector embeddings and textual content and provides built-in AI capabilities like keyword extraction, document intelligence, text translation, and text conversion.

A practical example of RAG at scale is Microsoft 365 Copilot. Copilot can work with PowerPoint, Word, Excel, and more. For instance, you could ask Copilot to create a PowerPoint presentation using content from Word documents stored in your OneDrive. Under the hood, Copilot takes your query, runs a similarity search across Microsoft Graph (which stores your organization’s documents, emails, and chat messages), retrieves relevant documents, and generates the presentation.

This is a real-world example of retrieval augmented generation, and it illustrates how RAG enables enterprise-ready AI applications that scale efficiently and maximize ROI.

In summary, RAG is a three-step pipeline: retrieval (fetching relevant documents), augment (creating a grounded prompt), and generation (producing responses). It allows AI agents to answer queries using enterprise knowledge, reducing costs, leveraging vector databases, and powering applications like Microsoft Copilot or other generative AI solutions.

# **B) What are Vector Embeddings ?**

In this video, we discussed what vector embeddings are and how they form the core foundation of RAG, or Retrieval Augmented Generation. Vector embeddings are numerical representations of words, sentences, images, or other forms of data in a high-dimensional space, which can extend to hundreds or even thousands of dimensions rather than the traditional three-dimensional x, y, z space. These vectors capture the semantic and contextual meaning of the data, ensuring that similar items are positioned closer together in this high-dimensional space. The primary goal of converting text, images, or words into embeddings is to extract the underlying semantic meaning and group similar concepts together based on intent and context. These embeddings are generated using text embedding models provided by Azure OpenAI, with one of the most common models being the Ada 002 embedding model, which produces vectors of 1536 dimensions. A higher number of dimensions generally results in a better semantic understanding of the data, but it also increases computational and storage costs, leading to a trade-off between accuracy and expense. These embedding models are deployed in the same way as GPT models in Azure OpenAI and operate on a pay-as-you-go pricing model based on the number of tokens processed, where tokens are units derived from text through a tokenization process used for cost calculation, training, and defining context windows. For example, when phrases like “canine companions say woof,” “feline friends say meow,” and “bovine buddies say moo” are converted into vector embeddings, phrases with similar meanings are clustered together in the vector space, while unrelated phrases such as “a quarterback throws a football” are placed far away due to their distinct semantic context. This clustering in high-dimensional space is made possible solely through vector embeddings. Different embedding models generate vectors of varying dimensions and costs, with higher dimensions generally costing more per thousand tokens. When a text is sent to an embedding model such as Ada 002, the response returned is an array of floating-point numbers ranging from negative to positive infinity, totaling 1536 values for that model. Once generated, these embeddings need to be stored, and Azure provides several native storage options for this purpose, including Azure AI Search (formerly Azure Cognitive Search), Azure Cosmos DB with vector search capabilities (currently in preview), and Azure Redis Cache with vector similarity. 

Azure AI Search supports approximate nearest neighbor search, hybrid search combining keyword and vector search, and can ingest and vectorize unstructured data such as PDFs, Word documents, text files, and even documents containing both text and images, making it ideal for semantic search and recommendation use cases. Azure Cosmos DB, a globally distributed NoSQL database, allows storing both document data and their corresponding vector embeddings together, reducing the need for complex ETL pipelines, and is well-suited for high-availability, low-latency, large-scale applications like real-time recommendation systems. Azure Redis Cache, on the other hand, is more suitable for smaller datasets or caching scenarios where ultra-low latency similarity searches are required. In a typical RAG architecture using Azure Cosmos DB, documents are first ingested and broken down, embeddings are generated for each document using an embedding model, and both the document data and embeddings are stored together. When a user submits a query, the query is converted into embeddings, which are then compared against stored document embeddings using similarity measures such as cosine similarity or dot product to retrieve the most relevant context. This contextual information is then sent along with the user query to a GPT model, which generates a final response that is accurate, contextual, and grounded in enterprise data. This entire process highlights how vector embeddings are central to enabling retrieval augmented generation, forming the backbone of modern AI search and conversational architectures.

# **C) What is Azure AI Search**

So with this video, let's discuss how we can implement retrieval augmented generation (RAG) with Azure AI Search. We’ll look at using Azure AI Search as both a native vector storage option and an information retrieval solution.

What exactly is Azure AI Search? Azure AI Search results contain only your data, which can include text inferred or extracted from images, as well as entities and key phrases through text analytics. A key capability of Azure AI Search is that you can feed unstructured documents—PDFs, Word documents, text files, PowerPoint presentations, Excel sheets, and more. Even if these documents include images, Azure Search indexes all of that information. It can handle multimodal data, meaning both text and images. Azure Search extracts images, generates captions, extracts key phrases, references to organizations, locations, and more.

Regarding data sources, Azure AI Search supports bringing in data in JSON format or via auto crawling from locations such as OneLake storage, Fabric, Blob Storage, and even Azure Cosmos DB. This gives you flexibility to ingest data from various structured or unstructured sources.

For search and analysis, Azure AI Search supports vector search, full-text search, and hybrid search. Hybrid search combines keyword matching with vector search, providing more relevant results for user queries.

In terms of AI enrichment, Azure Search utilizes an Azure AI resource in the backend. This is a multi-service AI resource that supports computer vision, language analysis, text recognition, linguistic analysis, and more. It supports 56 languages and features like phonetic matching.

Queries in Azure Search use Lucene syntax, similar to SQL queries. You can use this for searching text, performing autocomplete, or geo-filtering. The service also supports scaling, role-based access control, managed identities, and key management with Azure Key Vault. It integrates with Azure Machine Learning, Azure AI, and Azure OpenAI, which is particularly relevant when using RAG.

The workflow in Azure AI Search starts with defining your data source. An indexer chunks the data from your documents and sends it to a skill set. The skill set connects to your Azure AI resource to perform AI enrichment—analyzing text, generating captions, and extracting information. The enriched output is sent back to the indexer, which maps the data as key-value pairs into an index. This index allows the data to be queried efficiently using Lucene syntax.

So the three main components of Azure AI Search are:

Indexer – breaks documents into chunks and sends data to the skill set.

Skill set – performs AI enrichment like text analysis and image analysis.

Index – stores the structured output to be queried.

To implement RAG using Azure AI Search with a vector embedding engine in Azure OpenAI, the flow works as follows: Data is ingested into Azure AI Search, which sends it to the skill set. The skill set calls the vector embedding engine to generate embeddings, then returns them to the indexer. The indexer maps the embeddings and other data into the index.

When a user query comes in, it is vectorized using the vector embedding engine. The query performs a vector similarity search (or hybrid search) on the index, retrieving the most relevant documents. This contextual information is then sent as a prompt to a GPT engine, which generates a response. The response is returned to the user.

In this RAG flow, Azure AI Search acts as both a vector storage solution and an intelligent AI toolset, combining capabilities like text and image analysis with vector search functionality.

That’s the end of the video—this explains how to implement retrieval augmented generation using Azure AI Search.

# **D) Introduction to Multi-Modal RAG in Azure AI Search**

Alright, so back I am with yet another exciting module to the course. This one is pretty awesome as it focuses on the latest advancements in the Azure OpenAI world and the Azure AI Foundry ecosystem in general. We will also explore some very interesting use cases. By now, you’ve probably guessed what we are going to cover—multi-modal RAG. This module will demonstrate how to leverage all the capabilities of Azure AI Foundry to build a multi-modal RAG pipeline.

Previously, we focused on building a RAG-based chatbot that analyzed text, whether structured or unstructured. But what if your information is hidden within images or structured documents? For example, documents containing tables where the layout matters, bounding boxes that define where the text resides, and the need for precise context for your LLM, along with proper citations. That’s exactly what this module will cover.

Let’s start with a scenario to understand multi-modal RAG better. Imagine you are a software engineer or AI developer at Contoso Pharma, a global pharmaceutical firm. Compliance officers need to answer audit questions using evidence from PDFs (regulatory documents, safety reports), images (drug labels, scanned approvals), tables (clinical trial results), Excel sheets (structured data), and internal notes or emails. Previously, these tasks were time-consuming, error-prone, and often incomplete. The challenge here is to build a chatbot capable of handling structured, unstructured, and semi-structured data, such as text, images, and tables, to provide accurate answers.

A simple text-based RAG pipeline isn’t enough in this case. Some text could be embedded in images, or the images themselves might provide valuable insights. Multi-modal RAG solves this by allowing you to combine all types of content. In the Azure ecosystem, it’s fairly straightforward: you can enable multi-modal RAG in Azure AI Search with minimal configuration.

Here’s how it works end-to-end. Data ingestion occurs first, where PDFs, documents, and images are uploaded to Azure Blob Storage. These files are then indexed with Azure AI Search, which creates a hybrid + vector search index. When a user submits a query, vector embeddings are computed and compared against the indexed embeddings, retrieving the best context to feed into the chatbot. The chatbot then generates the answer using the LLM based on both the query and retrieved context—this is the essence of retrieval-augmented generation.

Let’s visualize what happens under the hood with multi-modal RAG in Azure AI Search. The pipeline has two types: simple image verbalization and advanced document intelligence. Focusing first on simple image verbalization: PDFs stored in Azure Blob Storage contain both text and images. Azure AI Search connects to the Blob Storage and acts as the data source. The search resource has three components: Skill Set, Indexer, and Index.

The Skill Set contains several skills. First, it extracts all text using OCR or other libraries. Second, it generates vector embeddings for the text content. Importantly, there’s an Image Verbalization Skill, which sends images to the GPT-4 engine. The engine generates descriptions of images, converting them into textual content. So by the end, you have the original text plus text generated from image descriptions. This text can then be used by the Text Embedding A002 model to generate vector embeddings.

The Indexer maps outputs from the Skill Set to fields in the Index, which stores key-value pairs. Developers can query the index to retrieve chunks for context to feed into the GPT engine for summarization and answer generation.

The second type—advanced document intelligence—builds on image verbalization but focuses on structured documents, like invoices. Here, layout matters. You want to preserve the position of text in tables, bounding boxes, and pages. This ensures accurate citations and proper context for the LLM, which is critical for responsible AI practices.

The pipeline remains similar: invoices are stored in Azure Blob Storage, the Skill Set contains both Image Verbalization and Text Embedding skills, and a new skill called Layout Detection is introduced. This skill uses Azure Document Intelligence’s layout API to extract bounding box coordinates (x1, y1, x2, y2, etc.) of each text segment. The resulting text, along with these coordinates, is passed to the embedding generation skill, producing vector embeddings. The Indexer maps everything into the index, ready for querying and generating context for the LLM.

At the end of this process, everything reduces to text—whether it was originally text, images, or structured tables. This text is then used for embedding generation, indexing, and retrieval to power the GPT engine, enabling accurate, multi-modal, context-aware answer generation.

I know this is a lot to take in, but it’s going to be an exciting module. The lab exercises will make everything clearer, as you’ll get to inspect the Skill Set and Indexer configurations, understand how each part functions, and see what happens under the hood. This hands-on exploration will solidify your understanding of multi-modal RAG in Azure AI.

Without further ado, let’s move on to the next set of videos and get into the practical labs.

# **E) Lab: Deploying RAG Infra on Azure (Hands-On Lab)**

In this video, we’ll take a look at how to set up our RAG (Retrieval-Augmented Generation) pipeline using AI Search and Foundry Agents. Specifically, we’ll focus on the infrastructure setup, which involves deploying all necessary resources in Azure. In the following videos, we will see the pipeline in action once the infrastructure is ready.

I’m working in the VS Code environment in my repository. The folder we’ll be using is AI Search RAG, which resides inside the Agent Service parent folder. This folder contains three main items: a .env file for environment variables, a zip folder containing PDF documents to be uploaded to Azure Storage, and a Jupyter Notebook file rag.ipynb, which we’ll use to build our chatbot on top of these documents.

The intended workflow is as follows: the PDF documents are first stored in Azure Blob Storage. Then, an Azure AI Search resource is created, with the storage account set as a data source. The documents undergo multimodal analysis, generating vector embeddings and creating an index. Once the index is ready, an AI Search tool is attached to the Foundry Agent. Everything will be done via code, allowing the agent to query the documents and provide chat-based interactions.

As part of the infrastructure setup, we need to deploy several resources. This includes creating a storage account and uploading the PDF documents, setting up an AI Search index, provisioning a GPT-4 engine for chat completions, and deploying a Text Embedding Ada 002 model to generate vector embeddings from the documents. These embeddings will then populate the AI Search index, making the content queryable by the Foundry Agent.

First, we deploy the Text Embedding Ada 002 model via the Foundry Studio. This model generates 1536-dimensional vector embeddings, which are compatible with AI Search. After deployment, the model provides a target URI and key for potential Python-based API calls. Additionally, a GPT-4 model is already deployed, which will serve as the chat completions model for the agent.

Next, we create a storage account in the Azure portal. In the same resource group as the project (Foundry Demo RG), we deploy a storage account named RAGStrAccountDemo in the Sweden Central region. The storage type is set to Azure Blob Storage (or Azure Data Lake Storage Gen2), with standard performance and geo-redundant storage (GRS). Once validation passes, the storage account is deployed.

Meanwhile, in our VS Code repository, we unzip the collateral folder, which contains six PDF documents. These documents describe a hypothetical travel company’s offerings in Dubai, Las Vegas, London, New York, and San Francisco, including hotel descriptions and images. This dataset is ideal for testing multimodal RAG, as it includes text and images that will be analyzed and included in the AI Search vector index.

With the storage account deployed, we enable anonymous access under the configuration settings to allow document uploads. Sometimes this setting requires multiple attempts to properly save. Once enabled, we create a container named docs, set the access level to public or container, and upload all six PDF files. Each document now has a publicly accessible URL, which can be opened directly in a web browser.

The next step is creating the AI Search resource. We deploy a new AI Search resource in the same resource group (Foundry Demo RG) and region (Sweden Central). For the pricing tier, we select the Basic tier, which supports 15 indexes, 5 GB vector quota per partition, 3 replicas, and 3 partitions. The estimated cost is around $70–$80 per month, so it’s important to delete the resource after the lab if it’s no longer needed. Once deployed, the AI Search resource provides a protected URL and authentication keys, which can be used to manage the resource.

At this point, the infrastructure setup is complete. We now have a storage account with uploaded PDF documents, a deployed GPT-4 model for chat completions, a deployed Text Embedding Ada 002 model for vector embeddings, and an AI Search resource ready to index the content. In the next videos, we’ll focus on indexing the documents, running multimodal analysis, generating vector embeddings, and connecting the AI Search tool to our Foundry Agent so that we can interact with our dataset via chat.

With that, the infrastructure setup portion is complete, and we’re ready to move forward with the next steps in building a fully functional multimodal RAG pipeline.

# **F) Lab: Creating the AI Search Index (Hands-On Lab)**

In this video, we’ll use the Azure AI Search resource that we deployed during the infrastructure setup and create a vector index using the documents uploaded to our Azure Blob Storage account. The goal here is to enable multimodal RAG by indexing both text and image-based content so that it becomes queryable through Azure AI Search.

I’m currently on the Azure AI Search resource in the Azure portal. From the Overview section, I click on the Import data option, which is part of the newer experience. This allows me to bring in data from multiple sources such as SharePoint, Table Storage, or Microsoft Loop. Since our documents reside in Azure Blob Storage, that’s the data source I select.

Once the data source is chosen, Azure AI Search asks for the key scenario. We are not interested in keyword search or simple RAG—instead, we select Multimodal RAG, which is exactly what we’re building. I then select my subscription, choose the storage account where the documents are stored (ragstraccountdemo), and point to the blob container named docs. Since the documents are stored at the root level, I leave the blob folder field empty and proceed to the next step.

At this stage, Azure validates the data source connection and registers it internally. We’ll later inspect how this data source is represented inside AI Search so that we fully understand what’s happening under the hood rather than just clicking through the UI.

Next comes content extraction, where two options are available: Default and Document Intelligence. The Document Intelligence option is useful when working with invoices, tax documents, or structured forms where preserving layout, tables, and bounding boxes is critical. It uses Azure AI Document Intelligence in the background to extract text along with layout metadata. However, since our documents are simple PDFs containing images and descriptive text—and not structured invoices or tables—we proceed with the Default extraction option.

Now we choose how images should be handled. There are two approaches: Image Verbalization and Multimodal Embedding. With image verbalization, the pipeline sends images to a large language model—specifically GPT-4—which generates a textual description of each image and extracts any visible text. That generated text is then vectorized and stored in the search index. With multimodal embedding, images and text are vectorized directly using a multimodal embedding model without generating textual descriptions.

For our use case, image verbalization is the better choice because users will submit text-based queries and expect text-based answers. This enables text-to-text similarity matching. Multimodal embedding would be more appropriate if users were submitting images as queries and searching for similar images, which is not our scenario. Therefore, we select image verbalization.

For image verbalization, we configure Azure AI Foundry as the resource, choose the Pay-As-You-Go subscription, and select our Foundry project (Udemy Demo Project). The model deployment used here is GPT-4, which will receive images and generate their descriptions. Authentication is handled via API key, and we make sure to enable the required checkbox before moving forward.

Next, we configure text vectorization. Again, we select Azure AI Foundry, choose the same project, and select the Text Embedding Ada 002 model deployment. This model generates 1536-dimensional vector embeddings, which are fully supported by Azure AI Search. Authentication is set to API key, and after enabling the required checkbox, we move to the next step.

The next configuration concerns image output location. During indexing, Azure AI Search extracts images from the documents and stores them in a blob container. We choose the same storage account and create a new container named images, setting the anonymous access level to container. Once created, we select this container and continue.

We are then presented with options related to advanced ranking and relevancy, including Semantic Ranker. Semantic Ranker enhances search results by understanding the nuance of language—for example, distinguishing between “capital” as a city versus “capital punishment.” While we’ll cover Semantic Ranker in more detail later during agentic retrieval demos, we enable it here and move forward.

Now we name our index. I choose multimodal-rag-demo, and Azure automatically applies the same naming convention to the index, indexer, and skillset. Once confirmed, I click Create, and Azure begins indexing the content.

After indexing completes successfully, we can see all three components created:

An Index named multimodal-rag-demo

An Indexer named multimodal-rag-demo-indexer

A Skillset named multimodal-rag-demo-skillset

Let’s first inspect the Skillset, which is the heart of the RAG pipeline. It defines the AI processing steps applied to the data. In total, six skills are configured. The first is the Document Extraction Skill, which extracts metadata such as document title, author, and whether the document contains images. If images are present, they are stored in a normalized images field and later mapped into the index.

The second skill is the Text Split Skill, which breaks document content into chunks of 2000 characters with a 200-character overlap. This chunking strategy ensures that semantic context is preserved across embeddings and enables efficient retrieval.

The third skill is a Chat Completion Skill, which sends extracted images—one at a time—to the GPT-4 model. The system prompt instructs the model to generate concise and accurate descriptions of images, figures, diagrams, or charts, while the user prompt explicitly asks it to describe the image. The output of this step is stored as verbalized image content.

Next is the Azure OpenAI Embedding Skill, which converts the text chunks into 1536-dimensional vector embeddings using the Text Embedding Ada 002 model. This happens for each chunk of text independently. A similar embedding process is applied to the image verbalization output, ensuring both text and image-derived descriptions are searchable in vector space.

The Indexer then maps all outputs from the skillset directly into the index. If you inspect the indexer’s JSON definition, you can see how fields from the skillset are mapped one-to-one into index fields.

The Index itself defines all searchable fields, including content ID, document title, content text, vector embeddings, image metadata, page numbers, and bounding polygons. Some fields are searchable, some filterable, some sortable, and others retrievable. You can also view the complete JSON definition of the index for full transparency.

Using Search Explorer, we can query the index—for example, searching for “Dubai.” The results show default relevance scores as well as semantic rerank scores, which are especially useful because they account for linguistic nuance. We can see document titles like DubaiBrochure.pdf, text content, and also entries generated from image verbalization.

When searching by document ID, we can clearly see GPT-4-generated image descriptions such as a description of the Burj Khalifa illuminated at night, along with their associated vector embeddings. This confirms that both text and image-derived content are successfully indexed.

The Data Source section shows that our Azure Blob Storage account is registered correctly. It serves both as the source of documents and as the destination for extracted images.

Finally, when we navigate back to the storage account and open the images container, we can see folders containing the extracted images. Each image has a publicly accessible URL, and opening it in a browser confirms that the images were correctly extracted from the PDFs and stored.

This brings everything together. We now have a fully functioning multimodal index in Azure AI Search, complete with text extraction, image verbalization, vector embeddings, semantic ranking, and searchable metadata. In the next videos, we’ll connect this index to Foundry Agents and enable conversational querying over our documents.

# **G) Lab: Creating the Multi-Modal RAG Agent (Hands-On Lab)**

Once our infrastructure is fully set up and the vector index has been created, the next step is to actually see everything in action. We do this by creating and interacting with our agent using a code-first approach, specifically through a Jupyter notebook.

I’m currently inside the AI Search folder, which sits under the Agent Service parent folder, and within that folder, I’ve opened the notebook that we’ll be working with. Before we can begin executing this notebook, there’s an important prerequisite: we must populate the required environment variables.

These environment variables include the Foundry project endpoint, the model deployment name, the Azure AI Search connection name, and the Azure AI Search index name. The first two values are already familiar, but the AI Search connection name and index name are new, and we need to retrieve them before proceeding.

To obtain the AI Search connection name, we need to first establish a connection between our Foundry project and the Azure AI Search resource. For this, I navigate to Foundry Studio, go to the Operate section, and then open the Admin Control Panel. From there, I select the project I’m currently working on—in my case, the Udemy Demo Project.

Inside the project settings, I click on Add Connection, choose Azure AI Search, and proceed by selecting the appropriate AI Search resource. After clicking Connect, the connection is established successfully. To verify this, I go to the Connected Resources section, where I can see the newly created connection. It uses API key authentication, displays the connection name, includes the API key, and shows the URI of the AI Search resource.

I then copy this connection name and paste it into the corresponding field in my .env file.

Next, we need the index name. For that, I switch to the Azure AI Search resource in the Azure portal, navigate to the Indexes section, and locate the index that contains our document embeddings. In this case, the index name is multimodal-rag-demo. I copy this value and update it in the environment variable file as well.

While I’m at it, I also grab the Foundry project endpoint from the Foundry home page and confirm the model deployment name, which is GPT-4—the model our agent will be built on. After updating all values, I save the file using Ctrl + S. This step is crucial—don’t forget to save.

With the environment variables in place, we’re now ready to begin executing the notebook.

The first step in the notebook is loading the environment variables from the .env file. These include the Foundry project endpoint, model deployment name, AI Search connection name, and AI Search index name. Next, we initialize a Foundry project client, which establishes a connection to our Foundry resource.

Since we’ll be invoking an agent, we also set up an OpenAI client. Before creating the AI Search tool for the agent, we need to retrieve the connection ID corresponding to our AI Search connection. To do this, we list all available connections and compare each connection’s name against the one defined in the environment file. When a match is found, we store its connection ID in a variable.

Once we have the AI Search connection ID, we move on to creating our RAG agent. We name the agent rag-agent, and this is where the agent definition becomes particularly important.

The agent instruction is straightforward:
“You are a helpful assistant that uses Azure AI Search to answer user queries in a RAG setup.”

To give this agent access to Azure AI Search, we attach an Azure AI Search Agent Tool. This tool is configured using the previously captured connection ID, the index name, and a query type set to VectorSemanticHybrid.

We use a vector semantic hybrid query because our index contains both vector embeddings and semantic ranking. This approach combines vector similarity with semantic understanding, allowing the search to capture contextual nuance and linguistic meaning. While it’s possible to use only vector search or only keyword search, hybrid search consistently delivers the best results for text-heavy RAG use cases.

We also configure the Top K value, which is set to 3. By default, Azure AI Search can return up to 50 matching documents per query, but passing all of them to an LLM would dramatically increase token usage and potentially degrade response quality. Instead, we restrict the agent to only the top three most relevant documents. Since our documents are relatively small, this value is sufficient. Finding the optimal Top K value often requires experimentation, but getting it right can significantly improve RAG performance.

Once the agent is created, we receive the agent name and agent ID. At this point, we can start interacting with the agent by creating a conversation ID, which also allows us to trace the interaction later in Foundry.

The first user query we ask is:
“What are the hotels offered by Margaritaville in Las Vegas State? Please include the sources.”

Explicitly asking for sources is important for transparency and traceability, as it forces the agent to list the document URLs from which it derived its answer.

We then initiate a conversation using the agent, passing in the conversation ID and the user query.

The agent responds by listing the hotels offered by Margaritaville in Las Vegas, including descriptions of the Volcano Hotel, Fountain Hotel, and Canal Hotel. It also lists the sources used, which are LasVegasBrochure.pdf and TravelCompanyInfo.pdf.

Next, we ask a second question using the same conversation ID:
“Tell me about the strategic board composition of Margaritaville Travel.”

This question targets a specific document that contains board-level information. As expected, the agent responds with the board composition:

Margie Long as CEO

Logan Reid as CFO

M. Elfman as CTO

Deepak Nadar as Strategic Director

The agent also cites the correct source: MargaritavilleTravelCompanyInfo.pdf, confirming the authenticity of the response.

To validate everything, we return to the Foundry portal, navigate to the Build section, and confirm that our RAG agent (version 1) has been created with an Azure AI Search resource attached.

In the Traces section, using the same conversation ID, we can see both interactions. For the first query, the total token count is 1244, and the trace clearly shows that the agent invoked the Azure AI Search tool. While the full search output isn’t displayed due to its size, we can confirm that the tool was used successfully.

Similarly, for the second query, the token count is 1534, and the trace shows the remote call made to Azure AI Search, followed by the agent synthesizing the final response.

And with that, we’ve successfully seen the Azure AI Search–powered multimodal RAG agent in action—from infrastructure setup to live querying, source tracing, and execution monitoring.

# **(V) API Management and AI Gateway**

# **A) API Management as API Gateway in Foundry**

Azure API Management (APIM) plays a critical role as the API gateway within Microsoft Foundry, and to understand its importance, it helps to first look at what Azure API Management is and why it exists. For many people, APIM is a relatively new Azure resource, but it addresses a set of long-standing challenges around API governance, security, lifecycle management, and developer enablement. In today’s technology landscape—especially in the era of AI agents—organizations are increasingly realizing that achieving a strong return on investment requires agents to perform real business logic. To do that effectively, agents must connect to enterprise knowledge and perform operations, and APIs are the primary mechanism that enables this connection.

APIs have been a foundational part of enterprise architectures since the early web era. They act as the connective layer between an organization’s services and data layer and the connected experiences that consume them. These connected experiences can include web applications, mobile apps, IoT devices, SaaS solutions, and now AI agents. APIs expose enterprise data and services in a programmatic, retrievable way, allowing different systems and experiences to interact in a controlled and scalable manner.

Managing APIs, however, involves addressing the needs of two distinct groups: publishers and developers. Publishers are responsible for building, maintaining, securing, and governing APIs, while developers consume these APIs to build applications and solutions. Publishers face challenges such as abstracting API development, securing and protecting APIs, managing the full API lifecycle from design through production, monitoring usage and performance, onboarding developers, and potentially monetizing APIs. Developers, on the other hand, struggle with discovering APIs, understanding endpoints, parameters, and methods, onboarding quickly, and accessing SDKs and documentation that help them integrate APIs efficiently.

API Management gateways exist to solve these challenges for both publishers and developers. While there are open-source and cloud-native API management solutions available across platforms like AWS and GCP, Azure provides a purpose-built solution in the form of Azure API Management. An APIM instance includes a developer portal where developers can sign in, discover APIs, subscribe to them, and consume them under different pricing or usage tiers. At the same time, APIM sits between the API consumer and the backend API, enforcing policies such as rate limiting, authentication, governance, and transformation, effectively mediating all interactions.

Publishers benefit from access to a publishing portal where they can manage the API lifecycle, apply policies, monitor usage, and define subscription and pricing tiers. This enables API monetization in consumer-facing scenarios or controlled internal consumption in line-of-business applications. From an enterprise standpoint, APIM provides centralized governance over APIs while simplifying developer onboarding and consumption.

Azure API Management is a mature and widely adopted platform. Microsoft was named a leader in the 2021 Gartner Magic Quadrant for full lifecycle API management. According to Microsoft’s statistics, APIM mediates approximately 4.65 trillion API calls per year with an 87% year-on-year growth rate. Around 840,000 APIs are managed through APIM, representing 72% year-on-year growth, and over 18,000 customers—including enterprises like Accenture, Mercedes-Benz, AccuWeather, Alaska Airlines, Mastercard, and Rockefeller—use the service across 54 regions worldwide.

When deploying Azure API Management, there are two broad pricing categories: the Consumption tier and the Developer, Basic, Standard, and Premium tiers. The Consumption tier requires no infrastructure provisioning, supports built-in autoscaling down to zero, operates with a shared management plane, and has no reserved capacity. In contrast, the other tiers provide dedicated management and data planes, reserved capacity, higher service-level agreements, and more control over scaling. For production workloads, organizations typically choose Basic, Standard, or Premium tiers depending on SLA and feature requirements.

Azure API Management supports the entire API lifecycle. APIs can be designed using OpenAPI specifications, developed using tools such as Visual Studio Code, and exposed as SOAP, REST, GraphQL, WebSocket, or other API types. Once developed, APIs can be secured using over 50 pre-built policies, including rate limiting, throttling, authentication, and authorization. Policies can validate subscription keys, enforce JWT validation, integrate with Azure Active Directory and managed identities, and control access at a granular level. APIs can then be published with defined subscription tiers and pricing models.

Beyond security and governance, APIM supports advanced operational capabilities such as circuit breaker patterns, fault tolerance, and regional failover. Integration with Azure Monitor, Application Insights, Log Analytics, and Azure Alerts allows organizations to collect logs, metrics, traces, and performance data. This data can be analyzed using Log Analytics queries or visualized in Power BI dashboards to provide stakeholders with insights into API usage, performance, errors, and cost.

APIM policies are a key differentiator. Organizations can implement rate limiting per subscription or key, restrict access by IP address, validate JWTs and identities, transform requests and responses (such as JSON to XML or vice versa), apply caching, enable cross-domain policies, and enforce schema validation. These policies are templated and can be applied with minimal configuration. APIM also supports Dapr integration for microservices running on Azure Kubernetes Service or Azure Container Apps.

Importantly, Azure API Management has expanded to support generative AI scenarios. Within the APIM publishing portal, there is native support for Azure OpenAI Service and Azure AI Foundry, now renamed Microsoft Foundry. In this architecture, APIM acts as the API gateway for agents and the tools they consume. Agents may be deployed as containerized workloads on AKS, Azure Container Apps, or exposed via web applications. These agents often rely on underlying APIs, plugins, or MCP servers to perform tasks.

APIM enables organizations to govern both access to the agents themselves and the internal APIs, plugins, and MCP servers that agents use. All standard API policies—such as authentication, rate limiting, monitoring, and transformation—can be applied uniformly. This allows enterprises to mediate interactions between users and agents, as well as between agents and their underlying tools, using a single centralized gateway.

For generative AI workloads, APIM supports advanced patterns such as load-balanced circuit breakers that route requests to alternate agent instances or regions if failures occur. It enables authentication and authorization before users can access agents, semantic caching to serve repeated queries faster and reduce token consumption, throttling and rate limiting to prevent abuse or denial-of-service scenarios, managed identity authentication via Microsoft Entra ID, continuous deployment, and API monetization through subscription tiers.

From a solutions architect’s perspective, Azure API Management fills a critical gap within Microsoft Foundry. While Foundry addresses enterprise concerns around network isolation, identity, access control, and data protection, APIM complements it by solving policy enforcement, monitoring, governance, and cost control. By applying fine-grained rate limits, throttling, and usage controls, organizations gain visibility into token consumption and operational costs while maintaining control over how agents and APIs are used.

In summary, Azure API Management serves as the API gateway layer within the Microsoft Foundry ecosystem, governing interactions between users, agents, and the underlying APIs and tools those agents depend on. It enables enterprises to secure, monitor, scale, and monetize APIs and AI agents in a consistent and production-ready manner, making it a foundational component of modern AI-driven architectures.

# **B) MCP (Model Context Protocol) - Deep Dive**

In this video, the goal is to understand what the Model Context Protocol (MCP) is from a high-level perspective. MCP has become a major buzzword in the AI agent ecosystem, and before diving into the technical details in later videos, it’s important to understand the fundamental problem it is trying to solve and where it fits into the architecture of AI agents.

To understand MCP, we first need to look at how generative AI applications evolved. When ChatGPT initially gained popularity around 2023, most generative AI applications were simple chatbots. These chatbots were conversational but not autonomous. You couldn’t instruct them to perform real-world actions like booking a flight from India to the US. Today, however, chatbots and AI agents are capable of performing such tasks, and the key enabler behind this autonomy is the use of tools or plugins. These plugins allow agents to interact with external APIs. For example, when you ask a chatbot to book a flight, it sends a POST request to a flight service provider’s API in the background. This ability to interact with APIs is what makes modern agents autonomous.

However, there is a major bottleneck in how these plugins are implemented today. To enable an agent to call an API, developers typically hardcode the API logic into their application. A common example is attaching a function to a foundational model like GPT-4.1. This function acts as a plugin that gives the model permission to call an API in real time. For instance, a chatbot might be given a function called get_weather, which retrieves real-time weather information for a location. The function definition specifies the function name, its description, and the parameters it accepts—such as a location string. When the model decides that this function is relevant, it dynamically fills in the parameter and executes the corresponding backend code.

Behind the scenes, this usually involves custom code written by the application developer. In the weather example, a Python function accepts the location parameter, calls one API to fetch latitude and longitude for that location, constructs a second API call using those coordinates, and then makes a GET request to retrieve the weather data. When a user asks for the weather in London, the model identifies that the get_weather function should be invoked, fills in the location parameter, executes the custom Python code, and returns the real-time weather information to the user.

The problem with this approach is that the application developer is not the API provider. If the API provider changes the endpoint URL, modifies query parameters, alters payload structures, or deprecates a method, the application breaks. The developer then has to react—often urgently—by reading updated documentation, rewriting code, and redeploying fixes, sometimes in the middle of the night. This is particularly problematic for business-critical applications where downtime is unacceptable. There is no strong contract between the API provider and the application developer, and any breaking change on the provider side directly impacts the agent.

This is exactly the problem that Model Context Protocol is designed to solve. MCP aims to remove the burden of maintaining brittle, boilerplate integration code from application developers and shift that responsibility back to the API developers themselves. With MCP, the API developer not only maintains the API but also provides an MCP server. Instead of an AI agent connecting to custom integration code written by the application developer, the agent connects directly to the MCP server. If the API provider changes URLs, query parameters, or request structures, they update the MCP server accordingly. The agent continues to work without requiring any changes to the application code.

From the application developer’s perspective, this means no custom integration code is needed at all—not even a single line. The agent simply connects to the MCP server, and the server abstracts away all API changes and complexities. This makes MCP a powerful abstraction layer and a standardized contract between API providers and AI application developers.

MCP can be thought of as a universal interface for AI agents—similar to how USB-C acts as a universal connector for hardware devices. A single chatbot can connect to multiple MCP servers, each exposing a different capability. For example, an agent can connect to a GitHub MCP server to access repositories, a MongoDB MCP server to query a database, a Slack MCP server to send messages, or a Gmail MCP server to read and send emails. MCP servers are already available or emerging for platforms such as GitHub, Gmail, Slack, Microsoft Learn, PayPal, Stripe, and other web and financial services, often with strong security controls.

MCP servers come in two main types: remote and local. Remote MCP servers are hosted and maintained by external providers and are accessed over the internet. For example, a Gmail MCP server would be deployed and maintained by Google. An AI agent connects to it using network protocols such as HTTP and server-sent events. Local MCP servers, on the other hand, run on the same machine as the AI application. These do not require internet calls and instead communicate using standard input/output mechanisms on the local host. A common example of a local MCP server is one that allows an agent to analyze and query files on the user’s local file system, keeping data private and confined to the user’s device.

At a high level, MCP follows a client–server architecture. The AI application or agent acts as the MCP client, while the MCP server exposes structured capabilities and context. This architecture allows developers to build reusable, modular connectors and attach them to agents with minimal effort.

To simplify everything with a real-life example, consider building a chatbot that acts like a personal Google Assistant. Without MCP, the developer would need to hardcode Gmail API calls to access inbox emails, sent items, and other data. If Google later updates the Gmail API—even slightly—the application risks breaking, and the developer must manually update the integration. With MCP, the developer simply connects the chatbot to the Gmail MCP server maintained by Google. All custom integration code is replaced by a single connection to the MCP server, and API changes are handled entirely by the API provider.

Despite its promise, MCP is still in its early stages. From both a development and security perspective, the ecosystem is still maturing. This is similar to the early days of large language models and AI agents, when issues like prompt injection attacks were not fully understood, and tools like Azure Content Safety emerged only later. MCP adoption is growing rapidly because it simplifies integration and introduces a standardized protocol, but it still lacks deep abstraction and requires strong coding skills to implement MCP servers effectively. As a result, MCP is currently better suited for pro-code developers rather than low-code users.

That said, MCP represents a significant step toward standardization and reliability in AI agent integrations. It establishes a clear contract between API providers and application developers, reduces operational risk, and simplifies long-term maintenance. This video provides a high-level introduction to MCP as a concept and as a solution to a widespread problem in the AI agent world. In the next set of videos, the focus will shift to exploring MCP in greater technical depth.

# **C) MCP Server Architecture**

All right, let’s now try to understand the Model Context Protocol (MCP) from an under-the-hood perspective. We’ll look at how MCP servers actually work, the methodology behind them, and how they power AI agents. To begin with, MCP follows a client–server architecture, where a client interacts with one or more MCP servers using a specific protocol—namely, the Model Context Protocol itself.

Since MCP is fundamentally a server, it requires a client that understands and follows the MCP protocol. In a typical setup, the client is your AI application. For example, when you use Claude and attach MCP servers to your agent, Claude becomes the MCP client. Similarly, in Visual Studio Code, when you configure GitHub Copilot to use MCP servers, VS Code acts as the MCP client. In both cases, these applications maintain connections to MCP servers in a standard client–server manner.

You can provide GitHub Copilot access to multiple MCP servers. Some of these servers might be local MCP servers connected to local data sources, while others might be remote MCP servers connected to external services. For instance, a local MCP server could expose data from a local database, whereas a remote MCP server might expose a set of web APIs over the internet. GitHub Copilot communicates with all of these servers using the MCP protocol, without the user needing to worry about how those APIs are implemented internally.

At its core, MCP allows a single host application to connect to multiple MCP servers simultaneously. When we go one level deeper, each MCP server connection is a one-to-one connection. For example, Visual Studio Code acts as an MCP host, and for every MCP server you configure, VS Code opens a separate connection. Internally, the VS Code runtime instantiates an MCP client object for each server, maintaining independent connections whether the server is local or remote.

Now let’s talk about the data layer and transport layer in MCP. MCP is primarily concerned with transferring data from servers to clients, because the client ultimately serves the large language model or chatbot. There are two key questions here: first, how does the client request data from the server, and second, how does the server transport that data back to the client?

The first question relates to the data layer. In traditional APIs, data is typically exchanged using JSON. A client sends a request, receives a JSON response, converts it into objects or dictionaries, and then applies business logic. JSON defines the structure and format of the data exchanged between the client and server.

However, MCP does not rely on plain JSON for its data layer. Instead, MCP servers and clients communicate using JSON-RPC (Remote Procedure Call). RPC is significantly faster and more efficient than plain JSON because it converts data into bytes and allows for compression, resulting in smaller payloads and reduced network overhead. While RPC is more complex to implement, it is widely used by large companies such as Google, Twitter, and LinkedIn for performance-critical systems.

Now let’s move to the transport layer, which defines how the data is actually transmitted from server to client. MCP servers can be either remote or local, and the transport mechanism depends on this distinction.

For remote MCP servers, communication used to rely on Server-Sent Events (SSE), but this has now been replaced by Streamable HTTP. Streamable HTTP is more efficient because it avoids long-running connections between client and server, which can place heavy load on the network. Instead, it provides a more optimized way of streaming data without maintaining persistent connections. In this course, all remote MCP servers will use Streamable HTTP.

For local MCP servers, Streamable HTTP is not required. Since the client and server are running on the same machine, communication happens through the standard input/output (stdin/stdout) stream. Every computer has this stream, which is the same mechanism used when you print output to a terminal using print in Python or console.log in JavaScript. In this setup, the client and MCP server exchange data directly through stdin/stdout without making any network calls or accessing the internet.

With this understanding of the client–server architecture, data layer, and transport layer, we can see that both MCP clients and MCP servers are currently somewhat difficult to implement due to limited abstraction. However, from a practical standpoint, the MCP client side is relatively easy, because tools like VS Code, GitHub Copilot, and Claude already provide prebuilt MCP clients. Building a custom MCP client from scratch would require significant effort, including implementing the protocol, data layer, and transport layer.

The harder part is building MCP servers, especially remote ones. This involves setting up infrastructure, potentially using Kubernetes or container apps, and deploying the MCP server as a microservice. Once deployed, managing this microservice becomes critical.

Key concerns include rate limiting, throttling, and secure access. These are essential for any production-grade MCP server. This is exactly the problem area addressed in the labs of this API management course. You’ll learn how to write an MCP server from scratch, deploy it to Azure Container Apps, and place it behind Azure API Management. From there, you’ll implement rate-limiting policies, authentication mechanisms, and security features such as API keys and JWT-based authentication.

In summary, while the MCP client side is largely handled for us by existing tools, the real challenge lies in building, deploying, and managing MCP servers at scale. That’s the area we’ll focus on going forward.

# **D) API Management and MCP Servers: Solution Architect's POV**

Before diving deep into the demos for MCP and Azure API Management, it’s important to first look at the bigger picture from a CTO’s perspective—a bird’s-eye view of what Azure API Management currently offers to help manage the overall infrastructure of MCP servers that an organization owns and controls.

At this point, we already have a general understanding of MCP servers, but there are several challenges that exist today. One major challenge is that development effort is only part of the problem. Even after building MCP servers, you still need to maintain the infrastructure that powers them. This infrastructure could involve running Kubernetes clusters, Azure Container Apps, or other container-based environments. Since MCP servers run as containers, they effectively become microservices, and microservices must be governed, controlled, throttled, rate-limited, and secured.

Another major challenge lies in security concerns. The AI agent ecosystem is still relatively new and rapidly evolving, which means it has not yet been thoroughly battle-tested from a security standpoint. MCP servers fall into the same category. One of the first security concerns is server trust. A malicious MCP server could impersonate a legitimate one, potentially leading to serious security breaches. This means organizations need a mechanism to identify and trust only approved MCP servers. Ideally, these trusted servers should be maintained in some form of central registry that developers within the organization can safely use.

The second security concern is credential management. MCP servers often interact with sensitive systems such as production databases. Storing tokens or credentials improperly makes them vulnerable to theft. If a malicious actor gains access to an MCP server that connects to production systems, the consequences could be severe. To mitigate this risk, security guardrails must be enforced at the API gateway level. This includes securing access using identity providers, JWTs, and other authentication and authorization mechanisms.

The third challenge is registry and discovery. Organizations need a centralized way to maintain a collection of hand-picked, trusted MCP servers. This registry should sit behind an API gateway and be accessible to all developers within the organization, allowing them to reuse approved MCP servers when building applications. These challenges together define the current pain points in the MCP and AI agent ecosystem.

One of the first solutions Azure API Management provides is the ability to expose existing MCP servers through an API gateway. For example, if you already have an MCP server deployed in Azure Container Instances, Container Apps, or a Kubernetes cluster, you can take its publicly accessible URL and place it behind an Azure API Management instance. This API Management instance acts as an API gateway that governs the MCP server, allowing you to apply policies such as rate limiting, request throttling, and identity-based access control.

This is something that will be explored in the labs for this module. You’ll run an MCP server inside an Azure Container App, expose its public URL, and then place it behind an API Management gateway. Once that’s done, you can consume this MCP server using an Azure AI Foundry agent through the Microsoft Agent Framework. This setup brings together several moving parts and provides a realistic, hands-on experience.

A key advantage of this approach is that API Management is cloud-agnostic. As long as an MCP server is remote and publicly accessible, it doesn’t matter whether it’s deployed on Azure, AWS, or GCP. You can take its URL, place it behind an API Management gateway, and enforce governance policies. By doing so, you gain flexibility, scalability, and centralized control over all MCP-based microservices.

The second major capability provided by Azure API Management is the ability to import existing REST APIs and expose them as MCP servers. Before MCP came into existence, organizations had already built countless REST APIs. The natural question now is whether those APIs need to be rebuilt using an MCP framework. Fortunately, the answer is no. Azure API Management allows you to take an existing REST API and, with minimal effort, convert it into a remote MCP server that AI agents can consume.

As long as you have a publicly accessible REST API URL, you can expose it as an MCP server using API Management. These exposed MCP servers can support both Server-Sent Events and Streamable HTTP, though Streamable HTTP is increasingly preferred because it avoids long-running connections and reduces network overhead. This approach allows organizations to reuse their existing APIs rather than discarding them, enabling a plug-and-play experience for AI agents.

Because all these MCP servers are placed behind an API gateway, organizations can consistently apply governance policies such as throttling, rate limiting, authentication, and scalability controls. This centralized governance model significantly simplifies infrastructure management while improving reliability and security.

Another critical aspect is securing MCP servers, and Azure API Management provides strong capabilities in this area as well. One particularly important setup—covered in an upcoming lab—involves securing MCP servers using OAuth and Microsoft Entra ID. In this flow, an MCP server deployed in an Azure Container App is placed behind an API Management gateway and accessed by an Azure AI Foundry agent.

Before the AI agent can access the MCP server, it must authenticate with Entra ID using an application ID. Entra ID handles authentication using OpenID Connect and authorization using OAuth, ultimately issuing a JWT (JSON Web Token). This JWT is then used to authorize requests to the MCP server through the API Management layer. If a request does not include a valid Entra ID–issued JWT, API Management rejects it with a 401 Unauthorized response. These authentication and authorization checks are enforced through API Management policies, which will be explored in detail during the labs.

The final challenge is maintaining a registry of trusted MCP servers, which is where the concept of an MCP Registry comes into play. This feature, currently in preview and implemented via Azure API Center, allows organizations to curate a set of approved MCP servers. Many companies—such as PayPal, Stripe, and Microsoft—already publish remote MCP servers. Using an MCP registry, organizations can select trusted servers and place them behind their API Management instance.

Instead of developers accessing MCP servers through public URLs, they use the API Management endpoint. This provides visibility into usage patterns, such as how many requests each MCP server receives, which applications are consuming them, and how many requests succeed or fail. It also enables logging, monitoring, and additional layers of authentication and governance.

Although the MCP registry concept is still evolving, it is a powerful idea and shows a lot of promise. Staying ahead of the curve in this space is important, and a brief demo of the MCP registry using Azure API Center will be shown to give a practical understanding of how it works.

In summary, this video focused on understanding the integration of MCP servers with API Management gateways from a CTO and solution architect perspective. It highlighted how Azure API Management addresses infrastructure management, security, governance, and scalability challenges in the MCP ecosystem.

# **E) Lab: Creating an AI Gateway in Foundry Project (Hands-On Lab)**

With this video, we will set up an AI Gateway in our Microsoft Foundry project. Before getting started, there is an important disclaimer. The AI Gateway feature is not available in all regions. I realized that it was not supported in the Sweden Central region, so I created a new Microsoft Foundry project in the East US region instead. The project is named “Foundry Demo East US”, and everything works perfectly there.
So before following along, make sure to check region compatibility and choose a supported region.

To begin, navigate to the Update section in Foundry. From there, go to Operate, and then open the Admin section. Inside Admin, you will see an option labeled AI Gateway. Click on it, and then select Add AI Gateway.

Next, you are asked to select the Foundry resource. In this case, I select Foundry Demo Project and choose to create a new AI Gateway. One important thing to note here is that the AI Gateway is free for the first 100,000 API requests. There is also a Pricing Details link available, which you can use to review the cost structure.

From the pricing information, you can see that:

The Basic tier costs around $150 per month

The Standard tier is approximately $700 per month

The Premium tier is about $3,000 per month

These prices are not cheap, but they make sense when you consider the return on investment. At scale, the AI Gateway helps you govern agents, APIs, and the entire AI ecosystem, which becomes critical in enterprise environments.

Once pricing is reviewed, we provide a name for the gateway. I name it “Foundry Gateway Demo”, and then click on Add. After this step completes, you can see that the AI Gateway has been successfully created.

When you open the gateway details, you can observe several important properties. It is using the Basic V2 pricing tier, which includes 100,000 free API requests, after which billing starts at $150 per month. You can also see the endpoint and the project name associated with this AI Gateway.

Now, let’s take a look at what happens behind the scenes. If you go to the Azure Portal and search for API Management, you will notice that an API Management instance has been automatically deployed with the same name as the AI Gateway. This confirms that the AI Gateway is built on top of Azure API Management.

Taking a quick walkthrough of the API Management instance, you’ll notice the API portal, which allows you to perform administrative tasks such as:

Governing agent-to-agent compatible agents

Bringing in large language models, including OpenAI models, as APIs

Defining rate limiting, throttling, and authentication policies

This setup is not limited to generative AI alone. If you already have existing HTTP REST APIs, you can bring them into API Management as well. Additionally, you can create and manage:

WebSocket APIs

GraphQL APIs

APIs from OpenAPI definitions

APIs defined using XML

SOAP APIs

OData APIs

If your backend APIs are hosted in Azure App Service, Azure Functions, Container Apps, or Logic Apps, you can directly bring them under the API Management governance boundary.

There is also a dedicated MCP Server section. This allows you to manage MCP servers under API Management. When creating an MCP server, you have two options:

Expose an existing MCP server hosted elsewhere

Convert an existing HTTP REST API into an MCP server without writing additional code

This is an extremely powerful feature. Many organizations have invested heavily in HTTP REST APIs over the years, and being able to convert them into MCP servers quickly means they can modernize their architecture without rewriting everything from scratch.

On the left-hand side of the API Management interface, you’ll also see Products and Subscriptions. These are used for monetizing APIs. You can bundle APIs into products such as Bronze, Silver, or Platinum tiers. Consumers purchase access to a product, receive a subscription, and authenticate using a primary and secondary access key. These keys are then used to securely call the underlying APIs.

This is essentially how everything works under the hood.

With that, we’ve successfully:

Created an AI Gateway in our Foundry project

Understood the pricing model

Explored the API Management instance that gets deployed automatically

Reviewed governance, MCP servers, and API monetization concepts

# **F) Lab: Capabilities of AI Gateway (Hands-On Lab)**

In this video, we take a quick look at some practical use cases of the AI Gateway to understand how it can be used effectively. To get started, we navigate to the Foundry portal. Under the Model section, we can see that a GPT-4 model is already deployed. By default, this model has certain rate limits associated with it based on the configuration used during deployment.

Now, suppose we want to change the rate limit or throttle requests based on a tokens-per-minute limit. This is exactly where the AI Gateway becomes useful. It allows us to control how many tokens per minute a large language model can consume, helping with cost control and quota management.

To configure this, we go to the Update section, then navigate to Admin, and from there access the AI Gateway section. We click on the AI Gateway instance that is already configured for our project. Inside the gateway, there is a Token Management area located next to the Projects section. This is where we configure token limits for our model deployments.

Here, we can see the deployed GPT-4 model, which currently does not have an explicit custom limit set. While a default limit exists based on deployment settings, no additional restrictions have been applied yet. By clicking Set Limit, we can select the project, choose the model deployment, and enter a numeric value to define a tokens-per-minute limit. Since the total allocated quota for this deployment is 40,000 tokens per minute, the configured value must be lower than that. Setting such limits helps prevent unexpected overuse and keeps token consumption under control.

Next, we look at another use case—governing existing MCP servers using the AI Gateway. For example, consider the Microsoft Learn MCP server, which is publicly accessible and commonly used by agents. To bring it under governance, we navigate to the API Management instance associated with the Foundry Gateway in the Azure portal.

Under the APIs section, we go to MCP Servers and select Create MCP Server, choosing the option to expose an existing MCP server. Here, we provide the base URL of the publicly available MCP server, such as the Microsoft Learn MCP endpoint. We assign a display name (for example, MS Learn MCP Server) and define a base path. The naming itself is flexible and does not impact functionality.

Once created, the MCP server is now exposed via the API Management gateway. At this point, the MCP server is governed through the gateway rather than being accessed directly. To make use of this governed endpoint, we update our tool configuration. We delete the existing direct MCP server connection and create a new custom tool connection using Model Context Protocol (MCP).

We then provide the MCP server name, paste the API Management endpoint, choose unauthenticated as the authentication type, and connect the tool. This ensures that all MCP requests now flow through the AI Gateway, allowing policies to be enforced.

After that, we attach this MCP server to an agent. We create a new agent, name it MCP Demo Agent, and add the MCP server as a tool. In the agent’s system prompt, we specify that the agent has access to the Microsoft Learn MCP server. Once saved, the agent is ready to use the governed MCP server.

We then test the setup by asking the agent for Microsoft Foundry code samples. The request is routed through the API Gateway and forwarded to the MCP server. After approving the tool invocation, we receive a valid response containing code samples and links from Microsoft Learn, confirming that everything is working as expected.

Next, we apply policies to the MCP server. Inside the API Management gateway, we open the MCP server and navigate to the Policies section. We apply a rate-limiting policy, which is sourced from a GitHub repository and pasted into the inbound policy section.

The policy limits calls to the MCP server based on a maximum threshold and renewal period. Initially, the threshold is set to 25 calls per 90 seconds, but we reduce it to 15 calls per 90 seconds for demonstration purposes. Once saved, this policy becomes active immediately.

To validate the policy, we open a new chat session and repeatedly send the same request to the agent. Since the agent uses the API Management endpoint, the rate-limiting policy is enforced automatically. After several consecutive requests—around the sixth or seventh attempt—we hit the rate limit and receive a 429 (Too Many Requests) error.

To make the effect even more visible, we can reduce the limit further (for example, to 2, 3, or 4 calls). In such cases, the rate limit is reached almost immediately, often within the second or third request. This clearly demonstrates how AI Gateway policies control traffic and protect backend services.

In summary, this demo shows how the Microsoft Foundry AI Gateway can be used to:

Control token usage for LLM deployments

Govern external MCP servers

Apply rate-limiting policies

Route agent traffic through a centralized, managed gateway

This was a quick but powerful overview of AI Gateway capabilities. With that, we conclude the demo and move on to the next set of videos.

# **G) Lab: Creating Our Own MCP Server in ACA (Hands-On Lab)**

In this lab, we will be creating our own MCP (Model Context Protocol) server, deploying it to Azure Container Apps, and then placing it behind an API Gateway so that it can be securely consumed by agents using a unified governance approach. The objective of this lab is to help you understand how to build an MCP server from scratch, containerize it, deploy it to Azure, and expose it securely through API Management.

To perform this lab, we will be working primarily with API Gateway and an instruction file named MCP 2.md, which contains the step-by-step instructions that we will follow throughout the lab. This lab involves several Azure components, so we will first walk through the overall architecture and flow before diving into the implementation.

The overall flow starts with setting up the required infrastructure in portal.azure.com. The first component we need to create is an Azure Container Apps Environment. Within this environment, we will deploy one or more Container App instances. These container app instances will host our remote MCP server.

As a side note, if you are interested in learning Azure Container Apps in more depth—especially AI-based use cases—I also have a dedicated course focused entirely on running AI workloads on Azure Container Apps.

Our MCP server will be a remote server, so we will use Streamable HTTP as the transport layer. The MCP server itself will be built using the FastAPI framework along with the FastMCP library. While I personally tend to use Flask for most backend APIs, FastAPI has significantly better support and examples for MCP servers, which is why it has been chosen for this lab. Many MCP code samples available online also use FastAPI, making it easier for you to reference external examples later.

Once the MCP server is ready, we will build a container image for it and push the image to Docker Hub or Azure Container Registry (ACR). For better security, we will use Azure Container Registry in this lab. After that, the image will be deployed to Azure Container Apps as a container app instance.

To clarify terminology:

An Azure Container Apps Environment acts as a logical boundary or “warehouse” that hosts multiple container app instances.

A Container App is similar to a lightweight compute unit that runs containers. It is not a virtual machine, but you can think of it as a logical unit that can run a main container and optional sidecars. In this lab, we only use a single main container, which hosts our MCP server.

With this understanding, we proceed to the first hands-on step: creating the Azure Container Apps environment using the Azure Portal.

Creating the Azure Container Apps Environment

We begin by navigating to portal.azure.com, searching for Container Apps, and selecting Create → Container App. We create a new resource group named Udemy App Demo RG. The container app name can be anything; for this lab, we use demo-container, as it is only a temporary instance used to validate the infrastructure.

The deployment source is set to Container Image, and we choose to create a new Container Apps Environment. The environment is named Udemy-demo-ACA-env. Zone redundancy is disabled, which is fine for this lab.

For workload profiles, we use the default profile, which provides 4 vCPUs and 8 GB memory. Since we are running only a lightweight MCP server, this is more than sufficient.

Monitoring settings are left at their defaults. Azure automatically provisions a Log Analytics workspace, which is acceptable. We do not explicitly configure Azure Monitor since our primary goal is to get the application running.

For networking, public network access is enabled, allowing incoming traffic from the public internet. No virtual network integration is required. After reviewing the settings, we proceed with Create.

This step provisions both the Container Apps Environment and a temporary quickstart container app instance. The initial deployment typically takes around 5–6 minutes because Azure sets up the environment and supporting infrastructure.

Once deployment completes, we navigate to the newly created container app. The Application URL is publicly accessible. When we open it in a browser, we see a simple Hello World response from the quickstart image, confirming that our infrastructure is working correctly.

MCP Server Code Overview

With the infrastructure ready, the next step is to build and deploy our MCP remote server.

The MCP server code resides under the server directory inside the MCP project folder. This directory contains:

A Dockerfile

Two JSON data files: courses.json and recipes.json

The main application file: server.py

A requirements.txt file

The courses.json file contains structured data about Udemy courses, including fields such as course ID, title, description, instructor, rating, reviews, duration, lectures, price in INR, category, and tags.

The recipes.json file contains recipe-related data such as recipe ID, name, description, ingredients, and cooking steps.

These JSON files act as a lightweight knowledge base for the MCP server.

MCP Server Implementation

The MCP server is implemented using FastAPI and FastMCP. The server is initialized with a name and bound to 0.0.0.0, allowing it to accept external traffic. It listens on port 8000.

MCP functionality is exposed through tools, which are defined using MCP tool annotations. Each tool represents a capability of the MCP server, such as querying JSON data or performing business logic. These tools are visible to MCP clients and language models, which decide when to invoke them based on tool names, descriptions, and outputs.

Examples of tools implemented include:

Fetching recipes by name

Fetching recipes by ID

Fetching courses

Fetching courses by ID

Fetching courses above a certain rating threshold

Each tool reads from the respective JSON file, performs a search, and returns structured data back to the MCP client or language model as context.

The MCP server is configured as a remote server using Streamable HTTP transport. The MCP endpoint is mounted at /mcp. This means that once deployed, appending /mcp to the container app URL routes traffic to the MCP server.

The requirements.txt file lists all dependencies required to build the container image successfully.

Creating Azure Container Registry

Before deploying the MCP server, we need a Container Registry. We create an Azure Container Registry (ACR) within the same resource group (Udemy App Demo RG) to simplify cleanup later.

The registry name can be anything (for example, acr). We choose the Basic pricing tier to minimize costs. Public access is enabled, encryption is left at default, and RBAC permissions are used.

Once created, we ensure that Admin user access is enabled in ACR. This is necessary for logging in via the Azure CLI when pushing images.

Building and Pushing the MCP Docker Image

We open the MCP instruction file in an integrated terminal and switch to a bash session. We then set environment variables for:

Azure Container Registry name

Resource Group name

Container Apps Environment name

Next, we navigate to the server directory where the Dockerfile is located. With Docker Desktop running, we build the image using the following naming convention:

<acr-name>.azurecr.io/udemy-demo-mcp-server:latest


After building the image, we log in to ACR using az acr login and push the image to the registry. Once completed, the image appears under Repositories in Azure Container Registry.

Deploying the MCP Server to Azure Container Apps

We now deploy the MCP server as a new Container App instance using the Azure CLI. The container app:

Uses the image from ACR

Runs in the previously created Container Apps Environment

Exposes port 8000

Has external ingress enabled

Maintains a minimum of one replica

Because ACR uses RBAC, we enable a system-assigned managed identity for the container app and grant it permission to pull images from ACR.

Within a few moments, the container app is successfully deployed and running. From the Overview section, we retrieve the application URL.

When we access the URL with /mcp appended, the browser displays an error stating that the client must accept text/event-stream. This is expected behavior because a browser is not an MCP client. The message confirms that the MCP server is running correctly and awaiting proper MCP requests.

Conclusion and Next Steps

At this point, we have successfully:

Created an Azure Container Apps Environment

Built an MCP server using FastAPI

Containerized the MCP server

Pushed the image to Azure Container Registry

Deployed the MCP server as a container app

Verified that the MCP endpoint is accessible

In the next video, we will take this deployed MCP server and place it behind Azure API Management, where we will apply policies and governance controls.

# **H) Lab: Adding Our MCP Server to AI Gateway (Hands-On Lab)**

In this video, we will attach the MCP server that we previously created from scratch and hosted on Azure Container Apps to our Azure API Management service, which acts as the API Gateway for the Microsoft Foundry portal.

To begin, I am logged into portal.azure.com and navigated to the API Management service that is acting as the API gateway. Inside the API Management resource, I move to the APIs section, where I can see the MCP Server option. This is where we will register and expose our MCP server through the gateway.

Before creating the MCP server entry, I already have the Azure Container Apps instance URL saved in a notepad. If I copy this URL, paste it into a browser, and append the /mcp path, it confirms that the MCP server is up and running. However, you will not see a meaningful response in the browser. This is expected behavior because browsers do not support the Model Context Protocol. The error message indicating that the client must accept an event stream is actually a good sign—it confirms that the MCP server is active and expecting an MCP-compliant client.

Next, I return to the API Management portal and click on Create MCP Server. Since this MCP server already exists and is hosted externally on Azure Container Apps, I select the option to Expose an existing MCP server.

In the configuration screen, I provide the Base URL of the MCP server. This is the same Azure Container Apps URL that we verified earlier, with the /mcp path appended. This tells API Management exactly where the MCP server endpoint is located.

For the Display Name, I enter Udemy Demo MCP Server. The Base Path is also set to udemy-demo-mcp-server. This base path will be used by API Management to route requests to this MCP server. Once these values are set, I click on the Create button.

After creation completes, the MCP server hosted in Azure Container Apps is now successfully onboarded into Azure API Management. If I navigate into the newly created Udemy Demo MCP Server entry, I can see the MCP server URL managed by the API gateway. From this interface, I also have the option to configure API Management policies, such as authentication, throttling, logging, and governance controls.

We will explore and apply those API Management policies in the next video.

With this step completed, we have successfully connected our Azure Container Apps–hosted MCP server to Azure API Management, enabling it to act as a secure, governed API gateway for use within the Microsoft Foundry portal.

# **I) Lab: Testing Rate Limiting Policy (Hands-On Lab)**

Now that our Azure Container Apps–hosted MCP server is up and running, the next step is to attach it to the Microsoft Foundry portal as an MCP tool. We will use the MCP server URL, which is protected by the API Management instance, and later use it within an agent. Additionally, we will implement a rate-limiting policy and observe it in action.

To start, I copy the MCP server URL and navigate to the Tools section in the Microsoft Foundry portal. I click on Connect Tool, select Custom, and choose Model Context Protocol before clicking Create. I provide the name Udemy Demo MCP Server and set the MCP server endpoint to the URL we copied earlier. For authentication, I choose Unauthenticated, and then click Connect to successfully register the MCP server with the Foundry portal.

Next, we integrate this tool with an agent. I create a new agent and name it Udemy MCP Agent, then click Create. Returning to the Tools section, I select the Udemy Demo MCP Server, choose the option to use this in an agent, and associate it with the agent I just created. Now, the MCP server is successfully added to the agent. I configure the agent by defining it as a helpful assistant with access to the MCP server. This agent is built on a GPT-4 model. After setting this up, I click Save to save the new version of the agent.

To test the integration, I ask the agent a query: “Can you tell me something about the recipe with ID six?” The system requests approval to invoke the MCP server function. After clicking Approve, the agent successfully retrieves the recipe: vegetable stir fry, along with its description, ingredients, and preparation steps. Next, I query the agent for “a list of all courses by Udemy instructor Singh Bakshi with average rating greater than 4.2”. After approval, the agent returns the relevant courses from the MCP server, confirming that the integration works correctly for multiple queries.

The next step is to apply a rate-limiting policy to the MCP server. I navigate back to the MCP server in the Foundry portal and access the Policy section. From my GitHub repository, I open the rate_limiting_policy.md file and copy the policy configuration, which limits inbound requests. I modify the threshold value to six requests with a renewal period set to 90 seconds, then click Save.

To test rate limiting, I rerun the query “Can you tell me something about the recipe with ID six?”. On the first run itself, an error occurs indicating that the threshold has been exceeded. This happens because the agent makes multiple backend API calls per single query—for example, calls to list tools, invoke the function, fetch the response, and requery tool metadata. Therefore, even a seemingly low threshold can be exhausted quickly. It is important to experiment with and fine-tune the rate-limiting value according to your business use case, which may require values like 15 or 25 depending on the expected load.

This video demonstrated how to bring your own MCP server under the API Management governance layer, integrate it with an agent, and apply a rate-limiting policy to control usage. These steps provide a robust way to securely expose your MCP server for controlled access while enabling experimentation and governance.
