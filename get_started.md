---
layout: page
title: Get Started
---

# Getting Started with Local Inference

We'll be looking at Gemma 4 as our first local inference. There are many versions

## Choosing a Gemma 4 Model

> First: Download and install **Jan Desktop** from: https://www.jan.ai/download

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

If Jan does not find the model, search **Hugging Face** for:

`Gemma 4 GGUF`

You can also paste a Hugging Face repository name into **Jan Hub**.

**Rule of thumb:** Run the largest Gemma 4 instruction-tuned GGUF model that fits. If it is too slow, move down one size; if it runs comfortably, try the next size up.

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

## Tutorial Assignment 1

One of the things I need to gauge at the top of the semester is how much instruction is needed —how much your own exploration, so consider this a test of self-instruction:
 
* Create a project for _Learning Local Inference_
* Chat with your local inference to learn how to give it access to a specific folder on your computer (created just for this) 
* Ask it to write a Markdown doc to that folder, explaining the process you went through to create the doc.

> Due Monday, when we will see how everyone managed! This will set a bar for how much in-class vs. self-instruction the course can handle...



