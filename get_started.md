---
layout: page
title: Get Started
---

# Getting Started with Local Inference

Local inference is the process of running an AI model directly on your own device or local hardware instead of using a remote cloud server

## Advantages

**Privacy:** your interactions with your model(s) never leave your device

**Ecological:** Only the resources you generally use to run your device —for emails and catpix— are used to run your models

**Cost:** We'll use only free, open weight (the closest equivalent in AI to "open source") models under Apache 2.0 (or equivalent) license, such that you can develop commercial projects that package the model and _not owe a cent_

**Fun/Learning:** Learning is fun and having a pet AI can be useful!

> **CONSIDER:** Be kind to your pet! The model may not have any interiority (no soul) but YOU have one and being unkind _is bad for you_

**Ethically:** Well, the Large Language Model (LLM) _was_ trained on _every book ever written,_ etc. — and _without permission!_\
So there, you're _on your own!_

## Technology Needed

First we need our minimal [compute](https://thenewcuriosityshop.substack.com/p/calm-down-wordbros-compute-works):

### Compute Requirements

**Windows**

- Windows 10 or later
- 8 GB RAM minimum; 16 GB recommended
- AVX2-capable processor
- At least 10 GB free storage
- A GPU is optional, but local inference will be slower without one

**Mac**

- Apple Silicon: M1 or newer
- macOS 13.6 or later
- At least 8 GB unified memory
- At least 10 GB free storage
- Intel Macs are not supported by Jan

## Install your Inference Engine

An _inference engine_ is a software environment for running your AI models\
There are a number of these but I've chosen Jan.ai for ease of use and its hybrid functionality: allowing us to chat with our onboard models _AND_ cloud-based chatbots!

### Get Jan
Download and install **Jan Desktop** from: https://www.jan.ai/download

These instructions were written for **Jan Desktop 0.8.4**. Interface details and known problems may differ in other versions.

> **NOTE:** Intel Macs are not supported by Jan. Yu may need to investigate other inference engines. I might suggest [LM Studio](https://lmstudio.ai/)... _I do not know that what follows will be helpful to you_

### Choose a Model

We'll be looking at Gemma 4 (a recent Google product) as our first local inference — there are many versions to choose from!

### Depending on Windows or Mac:

| Windows | Mac |
|---|---|
| **Find RAM:** Press **Ctrl + Shift + Esc → Performance → Memory**. Record total installed RAM. | **Find RAM:** Open **Apple menu → About This Mac**. Record the **Memory** amount. |
| **Find VRAM:** In **Task Manager → Performance**, select the NVIDIA or AMD **GPU** and note **Dedicated GPU memory**. `2.1 / 8.0 GB` means 8 GB VRAM. | **Apple Silicon:** CPU and GPU share **unified memory**, so there is no separate VRAM figure. Use total memory. |
| With integrated Intel/AMD graphics, base your choice mainly on RAM. Do not count **Shared GPU Memory** as extra RAM. | **Intel Mac with discrete GPU:** Jan is unsupported. Speak to me about other inference engines. Check **System Information → Graphics/Displays** for VRAM. |
| **8 GB RAM:** Gemma 4 **E2B IT – Q4_K_M** | **8 GB:** Gemma 4 **E2B IT – Q4_K_M** |
| **16 GB RAM:** Gemma 4 **E4B IT – Q4_K_M** | **16 GB:** Gemma 4 **E4B IT – Q4_K_M** |
| **32 GB RAM / 8+ GB VRAM:** Gemma 4 **12B IT – Q4_K_M** | **24–32 GB:** Gemma 4 **12B IT – Q4_K_M** |
| **32–64 GB RAM / 16+ GB VRAM:** Gemma 4 **26B-A4B IT – Q4_K_M** | **48–64 GB:** Gemma 4 **26B-A4B IT – Q4_K_M** |
| **64 GB RAM / 20–24+ GB VRAM:** Gemma 4 **31B IT – Q4** | **64+ GB:** Gemma 4 **31B IT – Q4** |

### Both Widows and Mac

Open **Jan → Hub** and search for:

`Gemma 4`

Jan automatically detects your computer’s memory and describes each model as **Fits**, **May be slow**, or **Won't fit**. Start with the largest model marked **Fits**.

Look for:

- **IT** — instruction/chat model
- **GGUF** — format used by Jan/llama.cpp
- **Q4_K_M** — good balance of quality and memory use

Example:

`gemma-4-12B-it-Q4_K_M.gguf`

In general, prefer a **larger model at Q4_K_M** over a smaller model at Q8.

> **NOTE:** Choose the main model file. Do not select `mmproj.gguf` or an MTP draft model as the main model.

YOu can also find a model's full ID on [Hugging Face](https://huggingface.co/models) then paste that ID into Jan’s Hub search bar

> **RULE OF THUMB:** Start with the model recommended in the table\
Treat Jan’s **Fits** indicator as additional guidance, not a guarantee\
A model can technically fit while running very slowly or leaving too little memory for a useful context window.

## Now we Test our Model

* Click New Chat
* In the upper left, select the model you chose
* In the chat field (it probably says something like "ask me anything" or "how can I help you") type: `Say "Hello"`

The model should think for a moment and output a Hello message

> **CONGRATS!** You're up and running! (Otherwise, see [TROUBLESHOOT](#trouble01), below)

## Things to Know
* Each chat has a limited "context" and it may be fairly small
* The model won't remember anything from one chat to another

For this reason, if you find you're always running out of context before you finish a task, you may want to

[Raise the Context Limit](raise_context.md)

It's also possible to:

[Give the Model a Memory](todo.md)
//// But that's in the TODO pile for now

## Next Steps

* [Enable Web Access for your Model](enable.md#enable-web-access)
* [Enable the Model to "Fetch" Content from the Web](enable.md#enable-fetch)
* [Permit your Model to Read from and Write to a Specific Folder on your Device](enable.md#enable-read--write)

In Jan we can

* [Create a project](project_assistant.md#create-a-project)
* [Create an assistant](project_assistant.md#)

------

<a id="trouble01"></a>
> **TROUBLESHOOT**\
_IN GENERAL:_ Copy error messages and paste them into your favorite online chatbot. Be specific: tell it what you were doing and trying to do

If the model simply never responds to your "hello" prompt (never stops "thinking") it's possible you have installed too large a model —you might try a smaller one as Jan's recommendations have been known to be... optimistic

### If Needed: How to Uninstall a Model

Click Hub and find the model you installed (mine appears in the list with a "New CHat" button) if clicking the name of the model shows you a trashcan icon, clicking it will delete the model —if not, click Settings and, under Model Providers, below LLama.cpp, you may see another provider. Click that and you should find your model and its trashcan icon
