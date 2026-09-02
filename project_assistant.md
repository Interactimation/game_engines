---
layout: page
title: Projects / Assistants
---

# Projects and Assistants

Projects are where we can organize our work

Projects support _Assistants_ which we can design to help us in our work

We give our Assistants _Instructions_ which teach it what we want it for and how to behave

Assistants can also read Files, documents which serve as a knowledge base for the Models

> **CONSIDER:** You can chat outside or inside a Project\
The Project has one Assistant at a time, but you can swap them out\
Every chat needs a Model but these also my be swapped out of a Project\
**So there are Chats, Projects, Models and Assistants, Instructions and Files plugging into each other**

## Create a Project

   * Click **New Project** in the left sidebar
   * Name the Project — _Suggest "Learning Local Inference"_ or similar
    * Our first Project might be just learning to use the systems we're putting in place
   * Assign the Assistant you just created
   * The Assistant's Instructions will apply to conversations in that Project

## Create an Assistant

   * Go to **Settings → Assistants**
   * Click **+**
   * Give the Assistant a descriptive name — _Suggest "Learning Assistant" or similar_
   * Add its **Instructions**: persistent rules describing its role, expertise, preferences, and behavior — _I may be able to supply a first set of Instructions. If not, suggest querying ChatGPT or Claude for a set of Instructions fit for the Model, and the Project. Be specific with your chatbot. You might go back and forth with this external advice, fine-tuning this set of Instructions over time. Eventually We hope to get an idea of what works for the Model!_
   * Save

**Select the Model**

   * Open a conversation in the Project
   * Use the **Model selector** in the chat interface
   * Select your downloaded Model
   * If necessary, use the gear beside the Model to adjust **Context Size**, **GPU Layers**, or other inference settings

**Add Project Files**

   * In the Project's **Files** panel, click **Add**
   * Add Markdown, PDF, DOCX, code, or other reference files — _Suggest any file at all, for now, I may supply you with or we may find docs later._
   * Jan chunks and indexes these as **Project Files**, making them available across conversations in that Project

**Start a new conversation**

   * Confirm the correct **Assistant** and **Model** are active
   * Begin chatting
   * New conversations in the Project share the Project's Assistant and Project Files

### Vocabulary

* **Model** — the LLM doing the inference: Gemma, Qwen, etc
* **Assistant** — persistent Instructions/configuration that tell a Model how to behave
* **Instructions** — the Assistant's standing system-level directions
* **Project** — a workspace containing related conversations, one assigned Assistant, and shared Project Files
* **Project Files** — documents indexed for retrieval across the Project

**Important distinction:** you do not really "apply a Model to a Project". You **assign an Assistant to the Project** and **select a Model for the chat**. The Assistant supplies the behavior; the Model supplies the intelligence
