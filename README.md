<div align="center">

# Dealpilot AI

### A configurable conversational assistant for customer engagement and sales workflows

[![Repository](https://img.shields.io/badge/GitHub-mubeen456%2FDealpilot--AI-181717?logo=github)](https://github.com/mubeen456/Dealpilot-AI)
![Python](https://img.shields.io/badge/Python-3.8%20to%203.11-3776AB?logo=python&logoColor=white)

</div>

## Overview

Dealpilot AI is a repository for exploring how language models can assist with customer conversations, product discovery and sales-oriented tasks. The underlying application uses conversation-state guidance and optional tools to help an assistant respond to changing buyer needs instead of relying on a fixed script.

This repository is based on the open-source [SalesGPT](https://github.com/filip-michalsky/SalesGPT) project. Dealpilot AI is the name used for this repository; the original Python package and import paths remain `salesgpt` unless the code is separately refactored. Features below describe capabilities in the upstream implementation, not independently verified outcomes or personal contributions.

## What the application can do

- **Follow the discussion:** Use a structured dialogue flow to manage introductions, customer requirements, product explanations and next steps.
- **Consult a product catalogue:** Use available agent tools to look up relevant items and details instead of answering solely from the model's general knowledge.
- **Support purchasing workflows:** Connect to payment-link generation where the required integrations and credentials have been configured.
- **Extend business communication:** Integrate with email, scheduling and other systems when those services are properly set up.
- **Work with different language models:** Use supported model providers through the project's LiteLLM integration.
- **Assist with testing and observability:** Use available tracing, evaluation and debugging tools during development.

Availability of particular functions depends on configuration, API access and the version of the code you are running.

## Typical conversation flow

1. A prospect starts a conversation or asks about an offering.
2. The assistant identifies the current stage and what the prospect wants to accomplish.
3. When appropriate, it queries configured business information or connected tools.
4. It generates a response grounded in the available context.
5. It asks for a sensible next step, or concludes the exchange when the prospect is finished.

## Implementation notes

The inherited codebase uses Python, the `salesgpt` package, LangChain-related components and LiteLLM. Optional integrations may require their own API keys and dependencies. See the source files and configuration examples for the definitive implementation details.

### Local requirements

- Python **3.8–3.11** (as specified by the source project's documented requirements)
- Git
- Credentials for the model provider and any optional integrations you choose to use

### Prepare a Windows environment

Open **Git Bash** in the project folder:

```bash
python -m venv env
source env/Scripts/activate
```

Install dependencies using the setup configuration included in the repository. The original project documents `make setup` for development installations; this requires Make to be available:

```bash
make setup
```

Create a local `.env` file using `.env.example` as a guide. Add only the credentials relevant to your chosen model or connected service. **Never commit `.env` or actual API keys.**

### Start the command-line example

From the project root, run:

```bash
python run.py --verbose True --config examples/example_agent_setup.json
```

The supplied example configuration may need to be adjusted for your model and integrations.

### Launch using containers

If Docker and Compose are installed and the repository includes the upstream Compose configuration:

```bash
docker-compose up -d --build
```

The upstream setup documents a chat interface at `http://localhost:3000/chat`. To shut it down:

```bash
docker-compose down
```

Container names, ports and instructions should be checked against the version of the project in this repository.

## Development checklist

- [ ] Confirm local setup and dependencies work
- [ ] Run at least one end-to-end conversation
- [ ] Replace sample catalogue and company details with non-sensitive test data
- [ ] Add automated tests for conversation transitions and tool responses
- [ ] Measure output relevance, answer grounding and response time
- [ ] Document original changes compared with the upstream codebase

## Reporting results

No user counts, sales conversion rates, benchmark accuracy, or response-time improvements are asserted here. Add tested measurements, methodology and screenshots only when you have evidence for them.

## Repository stewardship

Repository: [mubeen456/Dealpilot-AI](https://github.com/mubeen456/Dealpilot-AI)

This README describes a renamed repository built from existing open-source software. Updating documentation does **not** itself establish authorship of the underlying software. List any original extensions, custom integrations or experiments here after they are implemented.

## Attribution and license

Based on **SalesGPT**, originally maintained by **Filip Michalsky and contributors**:

- Original source: https://github.com/filip-michalsky/SalesGPT
- Original project license: MIT (see the upstream repository)

Retain the original repository's `LICENSE` file and any other required copyright notices when publishing this derivative. All trademarks and third-party services remain the property of their respective owners.
