# Getting Started with Local Inference

We'll be looking at Gemma 4 as our first local inference. There are many versions

# Choosing a Gemma 4 Model

First: Download and install **Jan Desktop** from: https://www.jan.ai/download

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

## For Both

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

