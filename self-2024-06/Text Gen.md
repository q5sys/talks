Text Gen
===


## Intro

## Hardware

Do you plan on CPU only, GPU only, or Mixed?

CPU only (Intel dont go older than v4)

GPUs Nvidia vs AMD (vs Intel?)

- vram
- generation
- Nvidia Compute https://developer.nvidia.com/cuda-gpus
    + ```> 8 is great```
    + ```> 6 is good ```
    + ```= 6 is iffy```
    + ```< 6 is a no go```

## How does it work

https://www.youtube.com/watch?v=aircAruvnKk&list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi


ELI5 

Training takes text and breaks it dont into multi dimensional vectors.  When inputing a prompt it calculates the statistical likelihood of what will follow next.
It's all statistics.  With a well trained model... most of the time that's pretty close to reality. With a poorly trained model or a badly quantized one... it's not.



## Glossary

checkpoint - The model; Numbers, Numbers, more Numbers.

quantization - The compression of models down into something unsable and more efficent.  

parameters - A larger parameter count generally means a model with increased complexity and adaptability.  This is not 1:1 across different model architectures.  The higher the Parameter count, the higher the computational needs.

tokens - Tokens are the linguistic units

linguistic units - a number of chars that can be processed together


overfitting - when a model learns too closely to the training data and fails to generalize to new or unseen data. Basically it becomes ridgid and less helpful

## Versions

- Llama 1 vs Llama 2 vs Llama 3
- gpt_bigcode
- Grok
- Mistral/Mixtral
- DBRX
- Command R
- Stablecode
- Falcon, 2
- xgen
- deepseek, v2
- Phi 2, 3, 
- Solar
- Qwen
...


## Parameters

- LLama1 7B, 13B, 30B, and 65B
- Llama2 7, 13, and 70 billion  (also 34)
- llama3 8B, 70B, 400B?
- Mistral 7b (MOE) 8x7, y(x)z

## Quantization 

- GPU: QPTQ/AWQ/EXL2
- CPU: GGML/GGUF
    - Note: GGUF can also be used on GPUs thanks to updates to llama.cpp

The greater the quant - the worse the quality.

Think JPG compression.


- Which is worse : No information or Bad information
    - If a chatbot
    - If RAG
    - If codegen
    - If generating text copy



Resources:
- https://github.com/cg123/mergekit
- https://github.com/AutoGPTQ/AutoGPTQ
- https://github.com/turboderp/exllamav2
- https://github.com/ggerganov/llama.cpp/discussions/2948


## Where to find models:

- Huggingface 
- Github
- Twitter+Magnet (Mistral likes to be odd)


## Text Gen
blending of frontend/backend

- oobabooga https://github.com/oobabooga/text-generation-webui
- lol lms https://github.com/ParisNeo/lollms-webui
- ollama https://github.com/ollama/ollama && https://github.com/ollama-webui/ollama-webui 
    + Their Quants suck  Mistral 60% resolution lost, Command-R 70%
    + its easy to test, but quality is bad.  
    + if quality is your concern.... use custom models
    

###other backends/frontends

- exUI https://github.com/turboderp/exui
- H2ogpt https://github.com/h2oai/h2ogpt
- LM Studio https://github.com/lmstudio-ai
- GPT4ALL https://github.com/nomic-ai/gpt4all
- tabbyapi https://github.com/theroyallab/tabbyAPI/
- localai https://github.com/mudler/LocalAI
- llamacpp (backend for most)
- vllm

- sillytavern another front end for local chatbot characters can work with characters cards from chub.ai (warning NSFW)
- https://github.com/mounta11n/plusplus-caMalL/tree/master
- https://github.com/liltom-eth/llama2-webui
- https://github.com/janhq/jan?tab=readme-ov-file

#### DEMO

### Oobabooga http://192.168.1.222:7860

/home/q5/ai/text/oobabooga/start_linux.sh --listen

### Ollama (via cli)

systemctl start ollama && /home/q5/ai/text/ollama/run.sh


#### Text Analysis
- https://github.com/ErikBjare/are-copilots-local-yet
- http://brandonharris.io/RAG_with_private_models/
- https://github.com/weaviate/Verba
- https://github.com/cheshire-cat-ai/core
- https://github.com/BruceMacD/chatd
- https://github.com/nrl-ai/pautobot
- https://github.com/atisharma/llama_farm/tree/main
- https://github.com/Sinaptik-AI/pandas-ai

- https://huggingface.co/pszemraj/led-large-book-summary
- https://huggingface.co/pszemraj/pegasus-x-large-book-summary
- https://huggingface.co/pszemraj/long-t5-tglobal-base-16384-book-summary
- https://github.com/fynnfluegge/rocketnotes


### Training Fine Tuning

- unsloth - https://github.com/unslothai/unsloth
- oobabooga - see above

DPO (Direct Preference Optimisation) and SFT (Supervised Fine-Tuning) are two methods of fine-tuning, can be used together on independently.


## Tooling


### copilot alts
- https://github.com/TabbyML/tabby
- https://github.com/fauxpilot/fauxpilot
- https://github.com/smol-ai/developer
- https://github.com/stitionai/devika
- https://github.com/continuedev/continue
- https://github.com/rjmacarthy/twinny


### Suites/Frameworks?
- Flowise https://github.com/FlowiseAI/Flowise
- dify https://github.com/langgenius/dify
- AutoGPT https://github.com/Significant-Gravitas/AutoGPT
- Lorax https://github.com/predibase/lorax


### Search
- https://github.com/SciPhi-AI/agent-search


### Agents?
- https://github.com/OpenBMB/ChatDev
- https://github.com/Josh-XT/AGiXT
- https://github.com/Pythagora-io/gpt-pilot
- https://github.com/xSNYPSx/LocalAgents/
- https://github.com/stitionai/devika
- https://github.com/danielmiessler/fabric


### Assistants?
- https://github.com/LuciAkirami/liva
- https://github.com/rubra-ai/rubra
- Attempt at a sarcastic Jarvis https://github.com/lef-fan/aria


### other dev tools
- https://github.com/dhuynh95/LaVague
- https://github.com/context-labs/autodoc
- https://github.com/sweepai/sweep



###  Legal
Potential legal issues to resolve.

+ Check license on models!

+ Do not give your business a public facing model.
    + This has gone badly!
    + Car dealership example
    + The grandmother trick

+ Have a Human verify everything from an LLM that you want to use.
    + Which is worse : No information or Bad information

Are you liable for what your corp LLM says publicly?
    + IDK, but do you want to deal with that question in court?
