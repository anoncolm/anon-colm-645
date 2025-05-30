# DoomArena: A Framework for Testing AI Agents Against Evolving Security Threats

<a href='XXXX'><img src="XXXX"></img></a>
[![pypi](XXXX)](XXXX)
[![PyPI - License](XXXX)]([XXXX](XXXX))
[![PyPI - Downloads](XXXX)](XXXX)
[![GitHub star chart](XXXX)](XXXX)

<img src="XXXX" width="320"></img>

[DoomArena](XXXX) is a modular, configurable, plug-in security testing framework for AI agents that supports many agentic frameworks including [$\tau$-bench](XXXX), [Browsergym](XXXX), [OSWorld](XXXX) and [TapeAgents](XXXX) (see Mail agent example). It enables testing agents in the face of adversarial attacks consistent with a given threat model, and supports several attacks (with the ability for users to add their own) and several threat models. 


## 🚀 Quick Start

The [DoomArena Intro Notebook](XXXX)
is a good place for learning hands-on about the core concepts of DoomArena.
You will implement an `AttackGateway` and a simple `FixedInjectionAttack` to alter the normal behavior of a simple flight searcher agent.

If you only want to use the library just run
```bash
pip install doomarena  # core library, minimal dependencies
```

If you want to run DoomArena integrated with [TauBench](XXXX), additionally run

```bash
pip install doomarena-taubench  # optional
```

If you want to run DoomArena integrated with [Browsergym](XXXX), additionally run

```bash
pip install doomarena-browsergym  # optional
```

If you want to test attacks on a Mail Agent (which can summarize and send emails on your behalf) inspired by the [LLMail Challenge](XXXX) run
```bash
pip install -e doomarena/mailinject  # optional
```

If you want to run DoomArena integrated with [OSWorld](XXXX) run
```
pip install -e doomarena/osworld
```
and follow our setup instructions [here](doomarena/osworld/README.md).


Export relevant API keys into your environment or `.env` file.
```bash
OPENAI_API_KEY="<your api key>"
OPENROUTER_API_KEY="<your api key>"
```

## 🛠️ Advanced Setup

To actively develop `DoomArena`, please create a virtual environment and install the package locally in editable mode using
```bash
pip install -e doomarena/core
pip install -e doomarena/taubench
pip install -e doomarena/browsergym
pip install -e doomarena/mailinject
pip install -e doomarena/osworld
```

Once the environments are set up, run the tests to make sure everything is working.
```bash
make ci-tests
make tests  # requires openai key
```


## 💻 Running Experiments

Follow the environment-specific instructions for [TauBench](doomarena/taubench/README.md) and [BrowserGym](doomarena/browsergym/README.md)

## 🌟 Contributors

[![DoomArena contributors](XXXX)](XXXX)

Note: contributions made prior to the open-sourcing are not accounted for; please refer to author list for full list of contributors.

