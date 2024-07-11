<div align="center">
  <a href="https://swarms.world">
    <img src="https://github.com/kyegomez/swarms/blob/master/images/swarmslogobanner.png" style="margin: 15px; max-width: 300px" width="50%" alt="Logo">
  </a>
</div>
<p align="center">
  <em>Multi-Agent Orchestration is incredibly painful swarms is making it simple, seamless, and reliable. </em>
</p>

<p align="center">
    <a href="https://pypi.org/project/swarms/" target="_blank">
        <img alt="Python" src="https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54" />
        <img alt="Version" src="https://img.shields.io/pypi/v/swarms?style=for-the-badge&color=3670A0">
    </a>
</p>
<p align="center">
<a href="https://twitter.com/swarms_corp/">🐦 Twitter</a>
<span>&nbsp;&nbsp;•&nbsp;&nbsp;</span>
<a href="https://discord.gg/agora-999382051935506503">📢 Discord</a>
<span>&nbsp;&nbsp;•&nbsp;&nbsp;</span>
<a href="https://swarms.world/explorer">Swarms Platform</a>
<span>&nbsp;&nbsp;•&nbsp;&nbsp;</span>
<a href="https://docs.swarms.world">📙 Documentation</a>
</p>


[![GitHub issues](https://img.shields.io/github/issues/kyegomez/swarms)](https://github.com/kyegomez/swarms/issues) [![GitHub forks](https://img.shields.io/github/forks/kyegomez/swarms)](https://github.com/kyegomez/swarms/network) [![GitHub stars](https://img.shields.io/github/stars/kyegomez/swarms)](https://github.com/kyegomez/swarms/stargazers) [![GitHub license](https://img.shields.io/github/license/kyegomez/swarms)](https://github.com/kyegomez/swarms/blob/main/LICENSE)[![GitHub star chart](https://img.shields.io/github/stars/kyegomez/swarms?style=social)](https://star-history.com/#kyegomez/swarms)[![Dependency Status](https://img.shields.io/librariesio/github/kyegomez/swarms)](https://libraries.io/github/kyegomez/swarms) [![Downloads](https://static.pepy.tech/badge/swarms/month)](https://pepy.tech/project/swarms)

[![Share on Twitter](https://img.shields.io/twitter/url/https/twitter.com/cloudposse.svg?style=social&label=Share%20%40kyegomez/swarms)](https://twitter.com/intent/tweet?text=Check%20out%20this%20amazing%20AI%20project:%20&url=https%3A%2F%2Fgithub.com%2Fkyegomez%2Fswarms) [![Share on Facebook](https://img.shields.io/badge/Share-%20facebook-blue)](https://www.facebook.com/sharer/sharer.php?u=https%3A%2F%2Fgithub.com%2Fkyegomez%2Fswarms) [![Share on LinkedIn](https://img.shields.io/badge/Share-%20linkedin-blue)](https://www.linkedin.com/shareArticle?mini=true&url=https%3A%2F%2Fgithub.com%2Fkyegomez%2Fswarms&title=&summary=&source=)

[![Share on Reddit](https://img.shields.io/badge/-Share%20on%20Reddit-orange)](https://www.reddit.com/submit?url=https%3A%2F%2Fgithub.com%2Fkyegomez%2Fswarms&title=Swarms%20-%20the%20future%20of%20AI) [![Share on Hacker News](https://img.shields.io/badge/-Share%20on%20Hacker%20News-orange)](https://news.ycombinator.com/submitlink?u=https%3A%2F%2Fgithub.com%2Fkyegomez%2Fswarms&t=Swarms%20-%20the%20future%20of%20AI) [![Share on Pinterest](https://img.shields.io/badge/-Share%20on%20Pinterest-red)](https://pinterest.com/pin/create/button/?url=https%3A%2F%2Fgithub.com%2Fkyegomez%2Fswarms&media=https%3A%2F%2Fexample.com%2Fimage.jpg&description=Swarms%20-%20the%20future%20of%20AI) [![Share on WhatsApp](https://img.shields.io/badge/-Share%20on%20WhatsApp-green)](https://api.whatsapp.com/send?text=Check%20out%20Swarms%20-%20the%20future%20of%20AI%20%23swarms%20%23AI%0A%0Ahttps%3A%2F%2Fgithub.com%2Fkyegomez%2Fswarms)








Swarms is an enterprise grade and production ready multi-agent collaboration framework that enables you to orchestrate many agents to work collaboratively at scale to automate real-world activities.

----

## Requirements
- `python3.10` or above!
- `.env` file with API keys from your providers like `OPENAI_API_KEY`, `ANTHROPIC_API_KEY`
- `$ pip install -U swarms` And, don't forget to install swarms!

## Install 💻

```bash
$ pip3 install -U swarms
```

---

# Usage Examples 🤖

Run example in Collab: <a target="_blank" href="https://colab.research.google.com/github/kyegomez/swarms/blob/master/playground/swarms_example.ipynb">
<img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

---

## `Agents`
A fully plug-and-play autonomous agent powered by an LLM extended by a long-term memory database, and equipped with function calling for tool usage! By passing in an LLM, you can create a fully autonomous agent with extreme customization and reliability, ready for real-world task automation!

Features:

✅ Any LLM / Any framework

✅ Extremely customize-able with max loops, autosaving, import docs (PDFS, TXT, CSVs, etc), tool usage, etc etc

✅ Long term memory database with RAG (ChromaDB, Pinecone, Qdrant)

```python
import os
from swarms import Agent, Anthropic


# Initialize the agent
agent = Agent(
    agent_name="Accounting Assistant",
    system_prompt="You're the accounting agent, your purpose is to generate a profit report for a company!",
    agent_description="Generate a profit report for a company!",
    llm=Anthropic(
        anthropic_api_key = os.getenv("ANTHROPIC_API_KEY")
    ),
    max_loops="auto",
    autosave=True,
    # dynamic_temperature_enabled=True,
    dashboard=False,
    verbose=True,
    streaming_on=True,
    # interactive=True, # Set to False to disable interactive mode
    saved_state_path="accounting_agent.json",
    # tools=[
    #     # calculate_profit,
    #     # generate_report,
    #     # search_knowledge_base,
    #     # write_memory_to_rag,
    #     # search_knowledge_base,
    #     # generate_speech,
    # ],
    stopping_token="Stop!",
    interactive=True,
    # docs_folder="docs",
    # pdf_path="docs/accounting_agent.pdf",
    # sop="Calculate the profit for a company.",
    # sop_list=["Calculate the profit for a company."],
    # user_name="User",
    # # docs=
    # # docs_folder="docs",
    # retry_attempts=3,
    # context_length=1000,
    # tool_schema = dict
    context_length=1000,
    # agent_ops_on=True,
    # long_term_memory=ChromaDB(docs_folder="artifacts"),
)

agent.run(
    "Search the knowledge base for the swarms github framework and how it works"
)

```

-----

### `Agent` + Long Term Memory
`Agent` equipped with quasi-infinite long term memory. Great for long document understanding, analysis, and retrieval.

```python
import os
from dotenv import load_dotenv
from swarms import Agent, OpenAIChat
from swarms_memory import ChromaDB

# Get the API key from the environment
api_key = os.environ.get("OPENAI_API_KEY")


# Initilaize the chromadb client
chromadb = ChromaDB(
    metric="cosine",
    output_dir="scp",
    docs_folder="artifacts",
)

# Initialize the language model
llm = OpenAIChat(
    temperature=0.5,
    openai_api_key=api_key,
    max_tokens=1000,
)

## Initialize the workflow
agent = Agent(
    llm=llm,
    agent_name = "WellNess Agent",
    name = "Health and Wellness Blog",
    system_prompt="Generate a 10,000 word blog on health and wellness.",
    max_loops=4,
    autosave=True,
    dashboard=True,
    long_term_memory=chromadb,
    memory_chunk_size=300,
)

# Run the workflow on a task
agent.run("Generate a 10,000 word blog on health and wellness.")


```
-----

### `Agent` ++ Long Term Memory ++ Tools!
An LLM equipped with long term memory and tools, a full stack agent capable of automating all and any digital tasks given a good prompt.

```python
import logging
from dotenv import load_dotenv
from swarms import Agent, OpenAIChat
from swarms_memory import ChromaDB
import subprocess

# Making an instance of the ChromaDB class
memory = ChromaDB(
    metric="cosine",
    n_results=3,
    output_dir="results",
    docs_folder="docs",
)

# Tools
def terminal(
    code: str,
):
    """
    Run code in the terminal.

    Args:
        code (str): The code to run in the terminal.

    Returns:
        str: The output of the code.
    """
    out = subprocess.run(
        code, shell=True, capture_output=True, text=True
    ).stdout
    return str(out)

def browser(query: str):
    """
    Search the query in the browser with the `browser` tool.

    Args:
        query (str): The query to search in the browser.

    Returns:
        str: The search results.
    """
    import webbrowser

    url = f"https://www.google.com/search?q={query}"
    webbrowser.open(url)
    return f"Searching for {query} in the browser."

def create_file(file_path: str, content: str):
    """
    Create a file using the file editor tool.

    Args:
        file_path (str): The path to the file.
        content (str): The content to write to the file.

    Returns:
        str: The result of the file creation operation.
    """
    with open(file_path, "w") as file:
        file.write(content)
    return f"File {file_path} created successfully."

def file_editor(file_path: str, mode: str, content: str):
    """
    Edit a file using the file editor tool.

    Args:
        file_path (str): The path to the file.
        mode (str): The mode to open the file in.
        content (str): The content to write to the file.

    Returns:
        str: The result of the file editing operation.
    """
    with open(file_path, mode) as file:
        file.write(content)
    return f"File {file_path} edited successfully."


# Agent
agent = Agent(
    agent_name="Devin",
    system_prompt=(
        "Autonomous agent that can interact with humans and other"
        " agents. Be Helpful and Kind. Use the tools provided to"
        " assist the user. Return all code in markdown format."
    ),
    llm=llm,
    max_loops="auto",
    autosave=True,
    dashboard=False,
    streaming_on=True,
    verbose=True,
    stopping_token="<DONE>",
    interactive=True,
    tools=[terminal, browser, file_editor, create_file],
    code_interpreter=True,
    # streaming=True,
    long_term_memory=memory,
)

# Run the agent
out = agent("Create a new file for a plan to take over the world.")
print(out)

```
----

### Devin
Implementation of Devin in less than 90 lines of code with several tools:
terminal, browser, and edit files.

```python
from swarms import Agent, Anthropic
import subprocess

# Model
llm = Anthropic(
    temperature=0.1,
)

# Tools
def terminal(
    code: str,
):
    """
    Run code in the terminal.

    Args:
        code (str): The code to run in the terminal.

    Returns:
        str: The output of the code.
    """
    out = subprocess.run(
        code, shell=True, capture_output=True, text=True
    ).stdout
    return str(out)

def browser(query: str):
    """
    Search the query in the browser with the `browser` tool.

    Args:
        query (str): The query to search in the browser.

    Returns:
        str: The search results.
    """
    import webbrowser

    url = f"https://www.google.com/search?q={query}"
    webbrowser.open(url)
    return f"Searching for {query} in the browser."

def create_file(file_path: str, content: str):
    """
    Create a file using the file editor tool.

    Args:
        file_path (str): The path to the file.
        content (str): The content to write to the file.

    Returns:
        str: The result of the file creation operation.
    """
    with open(file_path, "w") as file:
        file.write(content)
    return f"File {file_path} created successfully."

def file_editor(file_path: str, mode: str, content: str):
    """
    Edit a file using the file editor tool.

    Args:
        file_path (str): The path to the file.
        mode (str): The mode to open the file in.
        content (str): The content to write to the file.

    Returns:
        str: The result of the file editing operation.
    """
    with open(file_path, mode) as file:
        file.write(content)
    return f"File {file_path} edited successfully."


# Agent
agent = Agent(
    agent_name="Devin",
    system_prompt=(
        "Autonomous agent that can interact with humans and other"
        " agents. Be Helpful and Kind. Use the tools provided to"
        " assist the user. Return all code in markdown format."
    ),
    llm=llm,
    max_loops="auto",
    autosave=True,
    dashboard=False,
    streaming_on=True,
    verbose=True,
    stopping_token="<DONE>",
    interactive=True,
    tools=[terminal, browser, file_editor, create_file],
    code_interpreter=True,
    # streaming=True,
)

# Run the agent
out = agent("Create a new file for a plan to take over the world.")
print(out)
```
---------------

### `Agent`with Pydantic BaseModel as Output Type
The following is an example of an agent that intakes a pydantic basemodel and outputs it at the same time:

```python
from pydantic import BaseModel, Field
from swarms import Anthropic, Agent


# Initialize the schema for the person's information
class Schema(BaseModel):
    name: str = Field(..., title="Name of the person")
    agent: int = Field(..., title="Age of the person")
    is_student: bool = Field(..., title="Whether the person is a student")
    courses: list[str] = Field(
        ..., title="List of courses the person is taking"
    )


# Convert the schema to a JSON string
tool_schema = Schema(
    name="Tool Name",
    agent=1,
    is_student=True,
    courses=["Course1", "Course2"],
)

# Define the task to generate a person's information
task = "Generate a person's information based on the following schema:"

# Initialize the agent
agent = Agent(
    agent_name="Person Information Generator",
    system_prompt=(
        "Generate a person's information based on the following schema:"
    ),
    # Set the tool schema to the JSON string -- this is the key difference
    tool_schema=tool_schema,
    llm=Anthropic(),
    max_loops=3,
    autosave=True,
    dashboard=False,
    streaming_on=True,
    verbose=True,
    interactive=True,
    # Set the output type to the tool schema which is a BaseModel
    output_type=tool_schema,  # or dict, or str
    metadata_output_type="json",
    # List of schemas that the agent can handle
    list_tool_schemas=[tool_schema],
    function_calling_format_type="OpenAI",
    function_calling_type="json",  # or soon yaml
)

# Run the agent to generate the person's information
generated_data = agent.run(task)

# Print the generated data
print(f"Generated data: {generated_data}")


```
-----

### Multi Modal Autonomous Agent
Run the agent with multiple modalities useful for various real-world tasks in manufacturing, logistics, and health.

```python
# Description: This is an example of how to use the Agent class to run a multi-modal workflow
import os

from dotenv import load_dotenv

from swarms import GPT4VisionAPI, Agent

# Load the environment variables
load_dotenv()

# Get the API key from the environment
api_key = os.environ.get("OPENAI_API_KEY")

# Initialize the language model
llm = GPT4VisionAPI(
    openai_api_key=api_key,
    max_tokens=500,
)

# Initialize the task
task = (
    "Analyze this image of an assembly line and identify any issues such as"
    " misaligned parts, defects, or deviations from the standard assembly"
    " process. IF there is anything unsafe in the image, explain why it is"
    " unsafe and how it could be improved."
)
img = "assembly_line.jpg"

## Initialize the workflow
agent = Agent(
    llm=llm, max_loops="auto", autosave=True, dashboard=True, multi_modal=True
)

# Run the workflow on a task
agent.run(task=task, img=img)
```
----


### `ToolAgent`
ToolAgent is an agent that can use tools through JSON function calling. It intakes any open source model from huggingface and is extremely modular and plug in and play. We need help adding general support to all models soon.


```python
from pydantic import BaseModel, Field
from transformers import AutoModelForCausalLM, AutoTokenizer

from swarms import ToolAgent
from swarms.utils.json_utils import base_model_to_json

# Load the pre-trained model and tokenizer
model = AutoModelForCausalLM.from_pretrained(
    "databricks/dolly-v2-12b",
    load_in_4bit=True,
    device_map="auto",
)
tokenizer = AutoTokenizer.from_pretrained("databricks/dolly-v2-12b")


# Initialize the schema for the person's information
class Schema(BaseModel):
    name: str = Field(..., title="Name of the person")
    agent: int = Field(..., title="Age of the person")
    is_student: bool = Field(
        ..., title="Whether the person is a student"
    )
    courses: list[str] = Field(
        ..., title="List of courses the person is taking"
    )


# Convert the schema to a JSON string
tool_schema = base_model_to_json(Schema)

# Define the task to generate a person's information
task = (
    "Generate a person's information based on the following schema:"
)

# Create an instance of the ToolAgent class
agent = ToolAgent(
    name="dolly-function-agent",
    description="Ana gent to create a child data",
    model=model,
    tokenizer=tokenizer,
    json_schema=tool_schema,
)

# Run the agent to generate the person's information
generated_data = agent.run(task)

# Print the generated data
print(f"Generated data: {generated_data}")

```
----------------

### `Task`
For deeper control of your agent stack, `Task` is a simple structure for task execution with the `Agent`. Imagine zapier like LLM-based workflow automation.

✅ Task is a structure for task execution with the Agent. 

✅ Tasks can have descriptions, scheduling, triggers, actions, conditions, dependencies, priority, and a history. 

✅ The Task structure allows for efficient workflow automation with LLM-based agents.

```python
import os

from dotenv import load_dotenv

from swarms import Agent, OpenAIChat, Task

# Load the environment variables
load_dotenv()


# Define a function to be used as the action
def my_action():
    print("Action executed")


# Define a function to be used as the condition
def my_condition():
    print("Condition checked")
    return True


# Create an agent
agent = Agent(
    llm=OpenAIChat(openai_api_key=os.environ["OPENAI_API_KEY"]),
    max_loops=1,
    dashboard=False,
)

# Create a task
task = Task(
    description=(
        "Generate a report on the top 3 biggest expenses for small"
        " businesses and how businesses can save 20%"
    ),
    agent=agent,
)

# Set the action and condition
task.set_action(my_action)
task.set_condition(my_condition)

# Execute the task
print("Executing task...")
task.run()

# Check if the task is completed
if task.is_completed():
    print("Task completed")
else:
    print("Task not completed")

# Output the result of the task
print(f"Task result: {task.result}")
```

---





----


# Multi-Agent Orchestration:
Swarms was designed to facilitate the communication between many different and specialized agents from a vast array of other frameworks such as langchain, autogen, crew, and more.

In traditional swarm theory, there are many types of swarms usually for very specialized use-cases and problem sets. Such as Hiearchical and sequential are great for accounting and sales, because there is usually a boss coordinator agent that distributes a workload to other specialized agents.


| **Name**                      | **Description**                                                                                                                                                         | **Code Link**               | **Use Cases**                                                                                     |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------|---------------------------------------------------------------------------------------------------|
| Hierarchical Swarms           | A system where agents are organized in a hierarchy, with higher-level agents coordinating lower-level agents to achieve complex tasks.                                   | [Code Link](#)              | Manufacturing process optimization, multi-level sales management, healthcare resource coordination |
| Agent Rearrange               | A setup where agents rearrange themselves dynamically based on the task requirements and environmental conditions.                                                       | [Code Link](https://docs.swarms.world/en/latest/swarms/structs/agent_rearrange/)              | Adaptive manufacturing lines, dynamic sales territory realignment, flexible healthcare staffing  |
| Concurrent Workflows          | Agents perform different tasks simultaneously, coordinating to complete a larger goal.                                                                                  | [Code Link](#)              | Concurrent production lines, parallel sales operations, simultaneous patient care processes       |
| Sequential Coordination       | Agents perform tasks in a specific sequence, where the completion of one task triggers the start of the next.                                                           | [Code Link](https://docs.swarms.world/en/latest/swarms/structs/sequential_workflow/)              | Step-by-step assembly lines, sequential sales processes, stepwise patient treatment workflows     |
| Parallel Processing           | Agents work on different parts of a task simultaneously to speed up the overall process.                                                                                | [Code Link](#)              | Parallel data processing in manufacturing, simultaneous sales analytics, concurrent medical tests  |



### `SequentialWorkflow`
Sequential Workflow enables you to sequentially execute tasks with `Agent` and then pass the output into the next agent and onwards until you have specified your max loops.

```python
from swarms import Agent, SequentialWorkflow, Anthropic


# Initialize the language model agent (e.g., GPT-3)
llm = Anthropic()

# Initialize agents for individual tasks
agent1 = Agent(
    agent_name="Blog generator",
    system_prompt="Generate a blog post like stephen king",
    llm=llm,
    max_loops=1,
    dashboard=False,
    tools=[],
)
agent2 = Agent(
    agent_name="summarizer",
    system_prompt="Sumamrize the blog post",
    llm=llm,
    max_loops=1,
    dashboard=False,
    tools=[],
)

# Create the Sequential workflow
workflow = SequentialWorkflow(
    agents=[agent1, agent2], max_loops=1, verbose=False
)

# Run the workflow
workflow.run(
    "Generate a blog post on how swarms of agents can help businesses grow."
)

```

------

## `AgentRearrange`
Inspired by Einops and einsum, this orchestration techniques enables you to map out the relationships between various agents. For example you specify linear and sequential relationships like `a -> a1 -> a2 -> a3` or concurrent relationships where the first agent will send a message to 3 agents all at once: `a -> a1, a2, a3`. You can customize your workflow to mix sequential and concurrent relationships. [Docs Available:](https://swarms.apac.ai/en/latest/swarms/structs/agent_rearrange/)

```python
from swarms import Agent, AgentRearrange, Anthropic


# Initialize the director agent

director = Agent(
    agent_name="Director",
    system_prompt="Directs the tasks for the workers",
    llm=Anthropic(),
    max_loops=1,
    dashboard=False,
    streaming_on=True,
    verbose=True,
    stopping_token="<DONE>",
    state_save_file_type="json",
    saved_state_path="director.json",
)


# Initialize worker 1

worker1 = Agent(
    agent_name="Worker1",
    system_prompt="Generates a transcript for a youtube video on what swarms are",
    llm=Anthropic(),
    max_loops=1,
    dashboard=False,
    streaming_on=True,
    verbose=True,
    stopping_token="<DONE>",
    state_save_file_type="json",
    saved_state_path="worker1.json",
)


# Initialize worker 2
worker2 = Agent(
    agent_name="Worker2",
    system_prompt="Summarizes the transcript generated by Worker1",
    llm=Anthropic(),
    max_loops=1,
    dashboard=False,
    streaming_on=True,
    verbose=True,
    stopping_token="<DONE>",
    state_save_file_type="json",
    saved_state_path="worker2.json",
)


# Create a list of agents
agents = [director, worker1, worker2]

# Define the flow pattern
flow = "Director -> Worker1 -> Worker2"

# Using AgentRearrange class
agent_system = AgentRearrange(agents=agents, flow=flow)
output = agent_system.run(
    "Create a format to express and communicate swarms of llms in a structured manner for youtube"
)
print(output)

```

## `HierarhicalSwarm`
Coming soon...

## `GraphSwarm`
Coming soon...

## `MixtureOfAgents`
This is an implementation from the paper: "Mixture-of-Agents Enhances Large Language Model Capabilities" by together.ai, it achieves SOTA on AlpacaEval 2.0, MT-Bench and FLASK, surpassing GPT-4 Omni. Great for tasks that need to be parallelized and then sequentially fed into another loop

```python
from swarms import Agent, OpenAIChat, MixtureOfAgents

# Initialize the director agent
director = Agent(
    agent_name="Director",
    system_prompt="Directs the tasks for the accountants",
    llm=OpenAIChat(),
    max_loops=1,
    dashboard=False,
    streaming_on=True,
    verbose=True,
    stopping_token="<DONE>",
    state_save_file_type="json",
    saved_state_path="director.json",
)

# Initialize accountant 1
accountant1 = Agent(
    agent_name="Accountant1",
    system_prompt="Prepares financial statements",
    llm=OpenAIChat(),
    max_loops=1,
    dashboard=False,
    streaming_on=True,
    verbose=True,
    stopping_token="<DONE>",
    state_save_file_type="json",
    saved_state_path="accountant1.json",
)

# Initialize accountant 2
accountant2 = Agent(
    agent_name="Accountant2",
    system_prompt="Audits financial records",
    llm=OpenAIChat(),
    max_loops=1,
    dashboard=False,
    streaming_on=True,
    verbose=True,
    stopping_token="<DONE>",
    state_save_file_type="json",
    saved_state_path="accountant2.json",
)

# Create a list of agents
agents = [director, accountant1, accountant2]


# Swarm
swarm = MixtureOfAgents(
    name="Mixture of Accountants",
    agents=agents,
    layers=3,
    final_agent=director,
)


# Run the swarm
out = swarm.run("Prepare financial statements and audit financial records")
print(out)
```

----------

## Onboarding Session
Get onboarded now with the creator and lead maintainer of Swarms, Kye Gomez, who will show you how to get started with the installation, usage examples, and starting to build your custom use case! [CLICK HERE](https://cal.com/swarms/swarms-onboarding-session)


---

## Documentation
Documentation is located here at: [docs.swarms.world](https://docs.swarms.world)

----


## Docker Instructions
- [Learn More Here About Deployments In Docker](https://swarms.apac.ai/en/latest/docker_setup/)


-----

## Folder Structure
The swarms package has been meticlously crafted for extreme use-ability and understanding, the swarms package is split up into various modules such as `swarms.agents` that holds pre-built agents, `swarms.structs` that holds a vast array of structures like `Agent` and multi agent structures. The 3 most important are `structs`, `models`, and `agents`.

```sh
├── __init__.py
├── agents
├── artifacts
├── memory
├── schemas
├── models
├── prompts
├── structs
├── telemetry
├── tools
├── utils
└── workers
```

----

## 🫶 Contributions:

The easiest way to contribute is to pick any issue with the `good first issue` tag 💪. Read the Contributing guidelines [here](/CONTRIBUTING.md). Bug Report? [File here](https://github.com/swarms/gateway/issues) | Feature Request? [File here](https://github.com/swarms/gateway/issues)

Swarms is an open-source project, and contributions are VERY welcome. If you want to contribute, you can create new features, fix bugs, or improve the infrastructure. Please refer to the [CONTRIBUTING.md](https://github.com/kyegomez/swarms/blob/master/CONTRIBUTING.md) and our [contributing board](https://github.com/users/kyegomez/projects/1) to participate in Roadmap discussions!

<a href="https://github.com/kyegomez/swarms/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=kyegomez/swarms" />
</a>

----



## Swarm Newsletter 🤖 🤖 🤖 📧 
Sign up to the Swarm newsletter to receive  updates on the latest Autonomous agent research papers, step by step guides on creating multi-agent app, and much more Swarmie goodiness 😊

[CLICK HERE TO SIGNUP](https://docs.google.com/forms/d/e/1FAIpQLSfqxI2ktPR9jkcIwzvHL0VY6tEIuVPd-P2fOWKnd6skT9j1EQ/viewform?usp=sf_link)

## Discovery Call
Book a discovery call to learn how Swarms can lower your operating costs by 40% with swarms of autonomous agents in lightspeed. [Click here to book a time that works for you!](https://calendly.com/swarm-corp/30min?month=2023-11)


## Accelerate Backlog
Accelerate Bugs, Features, and Demos to implement by supporting us here:

<a href="https://polar.sh/kyegomez"><img src="https://polar.sh/embed/fund-our-backlog.svg?org=kyegomez" /></a>

## Community

Join our growing community around the world, for real-time support, ideas, and discussions on Swarms 😊 

- View our official [Blog](https://swarms.apac.ai)
- Chat live with us on [Discord](https://discord.gg/kS3rwKs3ZC)
- Follow us on [Twitter](https://twitter.com/kyegomez)
- Connect with us on [LinkedIn](https://www.linkedin.com/company/the-swarm-corporation)
- Visit us on [YouTube](https://www.youtube.com/channel/UC9yXyitkbU_WSy7bd_41SqQ)
- [Join the Swarms community on Discord!](https://discord.gg/AJazBmhKnr)
- Join our Swarms Community Gathering every Thursday at 1pm NYC Time to unlock the potential of autonomous agents in automating your daily tasks [Sign up here](https://lu.ma/5p2jnc2v)

---

# License
Apache License

# Citations
Please cite Swarms in your paper or your project if you found it beneficial in any way! Appreciate you.

```bibtex
@misc{swarms,
  author = {Gomez, Kye},
  title = {{Swarms: The Multi-Agent Collaboration Framework}},
  howpublished = {\url{https://github.com/kyegomez/swarms}},
  year = {2023},
  note = {Accessed: Date}
}
```

```bibtex
@misc{wang2024mixtureofagents,
    title={Mixture-of-Agents Enhances Large Language Model Capabilities}, 
    author={Junlin Wang and Jue Wang and Ben Athiwaratkun and Ce Zhang and James Zou},
    year={2024},
    eprint={2406.04692},
    archivePrefix={arXiv},
    primaryClass={cs.CL}
}
```

