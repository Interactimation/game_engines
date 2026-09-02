---
layout: page
title: Raise Context
---

# Raise the Context Size in Jan 0.8.4

1. Open **Settings → Model Providers**.
2. Find your Gemma model and **Stop** it.
3. Click the **gear icon** beside the model.
4. Turn **Fit to Hardware** (if you see it) **off**.
5. Turn **Speculative Decoding OR MTP** **off**.
6. Set **Context Size** to [**the next highest limit**](powers_2.md).
7. Start the model again.

> Do not change the context while the model is running. Jan may otherwise continue using the old value—or silently reduce it. The MTP setting can also trigger a model-loading error in Jan 0.8.4.

A larger context uses more RAM/VRAM. If the model will not load, reduce **Context Size** to **8192**.

## Check the Context Size

After restarting the model:

1. Open the model’s **gear icon**.
2. Confirm **Context Size** still reads **16384**.
3. For a definitive check, go to **Settings → General → App Logs → Open Logs**.
4. Open `app.log` and search for:

    ```text
    --ctx-size 16384
    ```

If the log instead shows `4096` or `8192`, the new setting was not applied. Stop the model, confirm **Fit to Hardware** is off, and start it again.

[Jan model-settings documentation](https://www.jan.ai/docs/desktop/model-parameters)