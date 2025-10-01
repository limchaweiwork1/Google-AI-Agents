# AI Personal Assistant Agent with Google ADK

This project contains a simple AI personal assistant agent built using the Google Agent Development Kit (ADK). The agent is designed to be a conversational AI that can answer user questions to the best of its ability.

## Purpose

The primary purpose of this agent is to serve as a foundational example of how to build AI agents with the Google ADK. It demonstrates the basic structure of an ADK project, including the agent's definition, configuration, and how to run it. This agent uses Google's `gemini-1.5-flash` model through the Vertex AI backend to understand and respond to user queries.

## Getting Started

Follow these instructions to get the agent up and running on your local machine.

### Prerequisites

*   Python 3.9 or higher
*   [uv](https://github.com/astral-sh/uv) - An extremely fast Python package installer and resolver.

### Installation & Configuration

1.  **Clone the repository:**
    ```bash
    git clone <repository-url>
    cd ai-agents-adk
    ```

2.  **Set up the Python environment:**
    This project uses `uv` to manage the virtual environment and dependencies. The necessary dependencies are listed in `pyproject.toml` and locked in `uv.lock`.

    Create the virtual environment and install the dependencies:
    ```bash
    uv venv
    uv sync
    ```

3.  **Configure your environment variables:**
    The agent requires Google Cloud credentials to function.

    *   Copy the example environment file:
        ```bash
        cp personal_assistant/.env.example personal_assistant/.env
        ```
    *   Edit the `personal_assistant/.env` file and add your Google Cloud project ID and location:
        ```
        GOOGLE_GENAI_USE_VERTEXAI=1
        GOOGLE_CLOUD_PROJECT=your-gcp-project-id
        GOOGLE_CLOUD_LOCATION=your-gcp-region
        ```

4.  **Set up Application Default Credentials (ADC):**
    The agent uses ADC to authenticate with Google Cloud services. Make sure you have the Google Cloud CLI installed and configured.

    Log in with your Google Cloud account:
    ```bash
    gcloud auth application-default login
    ```

## Usage

Once the setup is complete, you can interact with the agent in two ways:

### 1. Run in the Terminal

To chat with the agent directly in your terminal, run the following command from the `ai-agents-adk` directory:

```bash
uv run adk run personal_assistant
```

You can then type your questions and see the agent's responses. Type `exit` to end the session.

### 2. Run with the Development Web UI

The ADK includes a web-based interface for a more user-friendly chat experience. To launch it, run:

```bash
uv run adk web
```

This will start a local server, typically at `http://localhost:8000`. Open this URL in your web browser to interact with your personal assistant agent. The web UI also provides helpful debugging tools to inspect the agent's state and messaging events.