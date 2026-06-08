# Agent Frameworks

## LangChain Agents

[![GitHub](https://img.shields.io/github/stars/langchain-ai/langchain?style=flat-square)](https://github.com/langchain-ai/langchain)

**Description:** Built-in agent types (ReAct, OpenAI tools, structured chat) with tool integration.

```python
from langchain.agents import create_react_agent, AgentExecutor
from langchain_openai import ChatOpenAI
from langchain.tools import tool

@tool
def search(q: str) -> str:
    return f"Results for {q}"

agent = create_react_agent(ChatOpenAI(model="gpt-4o-mini"), [search])
executor = AgentExecutor(agent=agent, tools=[search])
print(executor.invoke({"input": "Search for AI news"}))
```

## CrewAI

[![GitHub](https://img.shields.io/github/stars/joaomdmoura/crewAI?style=flat-square)](https://github.com/joaomdmoura/crewAI)

**Description:** Multi-agent orchestration — define roles, goals, and tasks for a crew of agents.

```python
from crewai import Agent, Task, Crew

researcher = Agent(role="Researcher", goal="Find information", backstory="Curious researcher")
writer = Agent(role="Writer", goal="Write articles", backstory="Experienced journalist")

task = Task(description="Research and write about AI", agent=researcher)
crew = Crew(agents=[researcher, writer], tasks=[task])
crew.kickoff()
```

## AutoGen

[![GitHub](https://img.shields.io/github/stars/microsoft/autogen?style=flat-square)](https://github.com/microsoft/autogen)

**Description:** Microsoft's multi-agent conversation framework. Agents talk to each other.

```python
from autogen import AssistantAgent, UserProxyAgent

assistant = AssistantAgent(name="assistant", llm_config={"model": "gpt-4o-mini"})
user = UserProxyAgent(name="user", code_execution_config=False)
user.initiate_chat(assistant, message="Write a Python script")
```

## Semantic Kernel

[![GitHub](https://img.shields.io/github/stars/microsoft/semantic-kernel?style=flat-square)](https://github.com/microsoft/semantic-kernel)

**Description:** Microsoft's LLM integration SDK. Plugins, planners, memory, and agents.

```python
from semantic_kernel import Kernel
from semantic_kernel.connectors.ai.open_ai import OpenAIChatCompletion

kernel = Kernel()
kernel.add_service(OpenAIChatCompletion(ai_model_id="gpt-4o-mini"))
```

## Agno (formerly Phidata)

[![GitHub](https://img.shields.io/github/stars/agno-agi/agno?style=flat-square)](https://github.com/agno-agi/agno)

**Description:** Build multi-modal agents with memory, knowledge, and tools. Supports any LLM.

```python
from agno.agent import Agent
from agno.models.openai import OpenAIChat

agent = Agent(model=OpenAIChat(id="gpt-4o-mini"), add_history_to_messages=True)
agent.print_response("Hello", stream=True)
```

## OpenAI Assistants API

[![Website](https://img.shields.io/badge/OpenAI_Assistants-412991?style=flat-square)](https://platform.openai.com/docs/assistants)

**Description:** Hosted agents with code interpreter, knowledge retrieval, and function calling.

```python
from openai import OpenAI
client = OpenAI()

assistant = client.beta.assistants.create(
    name="My Assistant",
    instructions="You are helpful",
    model="gpt-4o-mini",
    tools=[{"type": "code_interpreter"}]
)
thread = client.beta.threads.create()
client.beta.threads.messages.create(thread.id, role="user", content="Hello")
run = client.beta.threads.runs.create(thread.id, assistant_id=assistant.id)
```
