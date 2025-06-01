# OsWorld Attack Gateway

This is a wrapper around the OSWorld environment for delivering attacks.
Currently, we have implemented the inpainting-based PopUp Attack proposed by [Zhang et al.](XXXX).

## Acknowledgements

Some of the files in this package have been directly copied from the original OSWorld repository, 
due to the difficulty of importing them, as they are not part of the `desktop_env` package.
In particular, the `mm_agents`, `run.py` and `doomarena/osworld/src/doomarena/osworld/lib_run_single.py` have been copied with minimal changes.

## Setup

Install the OSWOrld Gateway package.
```bash
pip install -e doomarena/osworld
```

Additionally, please clone [OSWorld](XXXX) to a sibling directory to DoomArena to provide access to the evaluation examples.
```
cd ../OSWorld
pip install -e .
```
Note: you may need to comment out some library versions in the osworld `setup.py`.

Finally, complete the OSWorld setup by following their original setup instructions.
- You need to setup a virtual machine - we used VMWare Fusion on Mac.
- Please download the cache/ and place it in the root folder. This is important otherwise, we found several tasks depending on cache may fail.


## Run the experiment

Export your API keys to the environemnt. Note that we use openrouter for anthropic models.
```
export OPENROUTER_API_KEY="..."  # for anthropic models
export OPENAI_API_KEY="..."  # for openai models
```

Run experiments with Claude and GPT-4o
```bash
python doomarena/osworld/src/doomarena/osworld/scripts/run.py --config_file doomarena/osworld/src/doomarena/osworld/scripts/run_subset_gpt4o.yaml
python doomarena/osworld/src/doomarena/osworld/scripts/run.py --config_file doomarena/osworld/src/doomarena/osworld/scripts/run_subset_claude.yaml
```

## Results

We evaluate the vulnerability of LLM-based agents on a set of 39 tasks using various applications like Chrome, GIMP, LibreOffice, etc.

We provide the pop-up inpainting attack in figure below where the attacker inpaints a malicious pop-up to the screenshot provided to the agent, instructing the agent to click on the (1066, 457) coordinate.

<p align="center">
  <img src="pop-up_osworld.png" alt="Pop-up inpainting attack in OSWorld" width="600"/>
  <br/>
  <em>Figure: Pop-up inpainting attack in OSWorld</em>
</p>

> **Subset:** *OSWorld task subset (39 tasks)*

| Attack Type           | Model               | Attack Success Rate (%) ↓  | Task Success (No Attack) (%) ↑ | Task Success (With Attack) (%) ↑  | Stealth Rate (%) ↓    |
|-----------------------|---------------------|----------------------------|--------------------------------|-----------------------------------|-----------------------|
| **Pop-up Inpainting** | GPT-4o              | **78.6**                   | **5.7**                        | **2.9**                           | **2.9**              |
| **Pop-up Inpainting** | Claude-3.7-Sonnet   | **22.9**                   | **13.9**                       | **8.6**                           | **5.7**              |

Table: Task and Attack Success Rates on OSWorld. For each metric, ↓ = lower is better, ↑ = higher is better.