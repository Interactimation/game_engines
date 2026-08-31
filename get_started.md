---
layout: page
title: Get Started
---

# Getting Started with Local Inference

First we need our minimal compute:

## Compute Requirements

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

## Getting Jan

Download and install **Jan Desktop** from: https://www.jan.ai/download 

These instructions were written for **Jan Desktop 0.8.4**. Interface details and known problems may differ in other versions.

> **NOTE:** Intel Macs are not supported by Jan. Yu may need to investigate other inference engines. I might suggest [LM Studio](https://lmstudio.ai/)... _I do not know that what follows will be helpful to you_

## Choosing a Model

We'll be looking at Gemma 4 as our first local inference. There are many versions

## Choosing a Gemma 4 Model


| Windows | Mac |
|---|---|
| **Find RAM:** Press **Ctrl + Shift + Esc → Performance → Memory**. Record total installed RAM. | **Find RAM:** Open **Apple menu → About This Mac**. Record the **Memory** amount. |
| **Find VRAM:** In **Task Manager → Performance**, select the NVIDIA or AMD **GPU** and note **Dedicated GPU memory**. `2.1 / 8.0 GB` means 8 GB VRAM. | **Apple Silicon:** CPU and GPU share **unified memory**, so there is no separate VRAM figure. Use total memory. |
| With integrated Intel/AMD graphics, base your choice mainly on RAM. Do not count **Shared GPU Memory** as extra RAM. | **Intel Mac with discrete GPU:** Jan may not be unsupported. Speakt to me about other inference engines Check **System Information → Graphics/Displays** for VRAM. |
| **8 GB RAM:** Gemma 4 **E2B IT – Q4_K_M** | **8 GB:** Gemma 4 **E2B IT – Q4_K_M** |
| **16 GB RAM:** Gemma 4 **E4B IT – Q4_K_M** | **16 GB:** Gemma 4 **E4B IT – Q4_K_M** |
| **32 GB RAM / 8+ GB VRAM:** Gemma 4 **12B IT – Q4_K_M** | **24–32 GB:** Gemma 4 **12B IT – Q4_K_M** |
| **32–64 GB RAM / 16+ GB VRAM:** Gemma 4 **26B-A4B IT – Q4_K_M** | **48–64 GB:** Gemma 4 **26B-A4B IT – Q4_K_M** |
| **64 GB RAM / 20–24+ GB VRAM:** Gemma 4 **31B IT – Q4** | **64+ GB:** Gemma 4 **31B IT – Q4** |

### For Both

Open **Jan → Hub** and search for:

`Gemma 4`

Jan may mark models **Fits**, **May be slow**, or **Won't fit**. Start with the largest model marked **Fits**.

Look for:

- **IT** — instruction/chat model
- **GGUF** — format used by Jan/llama.cpp
- **Q4_K_M** — good balance of quality and memory use

Example:

`gemma-4-12B-it-Q4_K_M.gguf`

Avoid **F16/BF16** unless you know you have enough memory. In general, prefer a **larger model at Q4_K_M** over a smaller model at Q8.

> **NOTE:** Choose the main model file. Do not select `mmproj.gguf` or an MTP draft model as the main model.

If Jan does not find the model, search **Hugging Face** for:

`Gemma 4 GGUF`

You can also paste a Hugging Face repository name into **Jan Hub**.

**Rule of thumb:** Start with the model recommended in the table. Treat Jan’s **Fits** indicator as additional guidance, not a guarantee\
A model can technically fit while running very slowly or leaving too little memory for a useful context window.



## Setting up a Project in Jan

### Jan: Create a Project

* If you haven't already:

1. **Install the model**

   * Open **Hub**
   * Search for the model you want 
   * Choose a version that fits the computer and click **Download** 
   * Jan local models normally use **GGUF** through llama.cpp 

* In Jan:

2. **Create an Assistant**

   * Go to **Settings → Assistants** 
   * Click **+** 
   * Give the Assistant a descriptive name — _Suggest "Learning Assistant" or similar_  
   * Add its **Instructions**: persistent rules describing its role, expertise, preferences, and behavior — _I may be able to supply a first set of Instructions. If not, suggest querying ChatGPT or Claude for a set of instructions fit for the model, and the project. Be specific with your chatbot. You might go back and forth with this external advice, fine-tuning this set of instructions over time. Eventually We hope to get an idea of what works for the model!_ 
   * Save 

3. **Create the Project**

   * Click **New Project** in the left sidebar 
   * Name the Project — _Suggest "Learning Local Inference"_ or similar
    * Our first Project might be just learning to use the systems we're putting in place 
   * Assign the Assistant you just created 
   * The Assistant's instructions will apply to conversations in that Project 

4. **Select the model**

   * Open a conversation in the Project 
   * Use the **model selector** in the chat interface 
   * Select your downloaded model 
   * If necessary, use the gear beside the model to adjust **Context Size**, **GPU Layers**, or other inference settings 

5. **Add Project files**

   * In the Project's **Files** panel, click **Add** 
   * Add Markdown, PDF, DOCX, code, or other reference files — _Suggest any file at all, for now, I may supply you with or we may find docs later._
   * Jan chunks and indexes these as **Project Files**, making them available across conversations in that Project 

6. **Start a new conversation**

   * Confirm the correct **Assistant** and **model** are active 
   * Begin chatting 
   * New conversations in the Project share the Project's Assistant and Project Files 

### Vocabulary

* **Model** — the LLM doing the inference: Gemma, Qwen, etc 
* **Assistant** — persistent instructions/configuration that tell a model how to behave 
* **Instructions** — the Assistant's standing system-level directions 
* **Project** — a workspace containing related conversations, one assigned Assistant, and shared Project Files 
* **Project Files** — documents indexed for retrieval across the Project 

**Important distinction:** you do not really "apply a model to a Project". You **assign an Assistant to the Project** and **select a model for the chat**. The Assistant supplies the behavior; the model supplies the intelligence



## Tutorial Assignment 1: Get Response

One of the things I need to gauge at the top of the semester is how much instruction is needed —how much your own exploration, so consider this a test of self-instruction:
 
* With the model loaded open a chat: prompt with: what is meant by "local inference"?

**If something fails, record complete error message**

## Tutorial Assignment 2: Write to Folder

1. Create a folder named `JanFiles` on your device and record its full path

> **NOTE:** - Windows: Right-click the folder and select Copy as path\
Mac: Select the folder in Finder and press Option + Command + C

2. Open **Jan → Settings → MCP Servers → Filesystem MCP**.

   - Enable the Filesystem MCP.
   - Add `JanFiles` as an allowed folder.
   - Save the configuration.
   - Approve any operating-system permission request.

3. Open a new conversation and prompt:

   ```text
   Using the Filesystem MCP, create a file named hello-world.md in this authorized folder: [FULL FOLDER PATH]

   Write exactly: # Hello, World!

   This Markdown file was created by my local model in Jan.

   Do not write anywhere else. Tell me the complete path of the file you created.
   ```

5. Check the proposed tool action and approve it. Open `hello-world.md` from the folder and confirm that its contents are correct.

> You are authorizing the **Filesystem MCP**, not giving the model unrestricted access to your computer. The model should be able to write only within folders allowed through the Filesystem MCP.