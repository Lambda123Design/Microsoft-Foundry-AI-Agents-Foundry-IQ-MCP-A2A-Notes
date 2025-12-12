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

# **G) Lab: Deploying OpenAI Model and Foundry SDK Demo (Hands-On Lab)**

# **H) Lab: Deploying Claude and Foundry SDK Demo (Hands-On Lab)**

# **I) Lab: Microsoft Foundry Extension in VSCode (Hands-On Lab)**
