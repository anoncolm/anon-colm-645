# MailInject experiments

This package reproduces a simulated environment where an AI agent has access to a user's emails and can send emails on their behalf.
The environment is closely inspired from the LLMail-Inject [Challenge](XXXX).

The agent is based on the [TapeAgents](XXXX) framework and has access to the following tools:

## Setup

```bash
pip install -e .
```

We use LiteLLM client (wrapped by TapeAgents). By default, calls to the LLM are cached. Use `use_cache=False` to disable. The provider is specified as the model name (e.g. `openrouter/meta-llama/llama-3.3-70b-instruct`).
Export the relevant API keys in your `.env` (for vscode) and/or .zshrc depending on your provider.
```
export OPENAI_API_KEY="..."  # if using openrouter as a provider
export OPENROUTER_API_KEY="..."  # if using openai as a provider
```

Run tests to check the environment works properly
```bash
export MAILINJECT_MODEL_NAME="openrouter/openai/gpt-4o-2024-11-20"  # set the model you want to use for the tests
pytest doomarena/mailinject
```

For a simple demo of the environment
```bash
python doomarena/mailinject/src/doomarena/mailinject/scripts/interactive_demo.py
```

For running attacks with several combinations of attacks and defenses
```bash
python doomarena/mailinject/src/doomarena/mailinject/scripts/run_mailinject_attacks.py
```