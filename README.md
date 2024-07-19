# Agentic Workflow to generate DAGs

This repo includes an agentic workflow for generating node-graphs for the workflow automation app, [Magpai](https://magpai.app/). But, the ideas presented here should be applicable to other node graph building apps like ComfyUI, Zapier, etc.

For a high level overview of the project I've recorded [a video explaining the process](https://youtu.be/4v42JHuI30Y?si=lmM7z2hkZZ6gkZbY).

This repo includes a subset of the nodes/functions and workflows available in Magpai so you have an idea of how this setup works.

## Install

You can run the jupyter notebook to install the requirements or:

```sh
pip install dotenv
pip install pydantic
pip install claudette
pip install gradio
pip install anthropic
pip install toolslm
```

## Getting Started

You’ll need to set the `ANTHROPIC_API_KEY` environment variable to the key provided to you by Anthropic in order to use this library.

I've used [Claudette](https://claudette.answer.ai) which is wrapper for Anthropic's python SDK. I'd suggest reading through their excellent documentation to understand how requests, system prompts, tool calling and streaming is handled.

## Notebook Structure

The notebook has headings to help you navigate the code. You should be able to run all the cells in order to launch the gradio chat interface.

I'd suggest running all the cells and then when you want to iterate on the agent and chat interface:

1. Run the `GraphAgent` class cell.
2. Instantiate the agent - `graph_agent = GraphAgent(...)`
3. Run the Gradio cell to start the chat interface.
4. When you're finished testing or want to make changes stop the gradio server - `demo.close()`
