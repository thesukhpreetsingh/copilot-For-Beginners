# Today I am setting up copilot locally.

## **You ask what is COPILOT?**

Microsoft Copilot is an AI-powered assistant and chatbot developed by Microsoft. Designed to boost productivity, it answers questions, summarizes documents, writes text (like emails and code), generates images, and automates repetitive tasks. It uses advanced machine learning and natural language processing to assist you.

Copilot in organization based system is already set up. It connects to a pre-configured cloud server with a menu of models built-in


So the best way to do and try everything on your local system is to - 
```
# use and install any open-weights or open-source AI model locally in Visual Studio Code.
# Because the models run entirely on your computer's hardware, your usage is 100% free and unlimited,
# with no monthly prompt quotas or credit limits.
```

To do this, you will need to install a local AI extension in VS Code and a local model runner on your machine.Popular Local Models You Can Install for your setup depends on your computer's RAM and graphics card (VRAM).
* **`Qwen2.5-Coder (1.5B, 7B, or 32B):`** _Currently considered the gold standard for local coding. The 7B version strikes the best balance between speed and logic for most modern laptops._

* **`DeepSeek-Coder-V2 (16B or 236B):`** _Highly advanced for complex coding tasks, but requires a powerful machine with a lot of VRAM to run efficiently._

* **`Llama 3.1 or Llama 3.3 (8B or 70B):`** _Meta's general-purpose models, which are excellent for software architecture explanations, documentation, and debugging._

* **`Codellama (7B or 13B):`** _An older but stable code-focused model from Meta._
* **`Phi-4 or Phi-3.5-mini (3.8B):`** _Microsoft’s lightweight models. They are incredibly fast and ideal for older computers or laptops without dedicated graphics cards._


## _**To download and run these models on your hard drive, you need a background engine. The easiest and most popular choice is Ollama**_

## Step 1: Install the Local Model Runner/ Enginer (Backend)

Download and install Ollama. Open your computer's Terminal (macOS/Linux) or Command Prompt (Windows).
Run the following following command.
```
irm https://ollama.com/install.ps1 | iex
```

On successfully running above command it will show something like
```
>>> Downloading Ollama for Windows...
######################################## 100.0%
>>> Installing Ollama...
>>> Install complete. Run 'ollama' from the command line.
```

Now that you've installed the engine, you can download and pull any engine respect to your needs or system configurations of your system ie what your system is capable of.
| Model Size  | Minimum RAM / VRAM | Best For |
| ------------- |:-------------:|:-------------:|
| 1.5B to 4B (e.g., Phi-4, Qwen 1.5B)| 8 GB RAM|Standard laptops, older computers, ultra-fast autocomplete.|
| 7B to 8B (e.g., Qwen 7B, Llama 8B)| 16 GB RAM (or 8GB VRAM)     |Modern Macbooks (M1/M2/M3) and PCs with dedicated GPUs.|
| 14B to 32B (e.g., Qwen 32B) | 32 GB RAM (or 16GB VRAM) |High-end workstation PCs or Mac Studios.|
##### Here B stands for Billion of tokens that these models are trained on 

## Step 2: Tell your computer to download the models
Run the following caommand on command shell
```
ollama pull qwen2.5-coder:7b
```
* Choose the model respect to your needs. Use ChatGPT to reason with.
* Share your hardware specifications to ChatGPT.
* Purpose you want to use for like **`I do coding and a lot of brainstorming`** so I was recommended to use **QWEN 2.5**  (7B or 14B version) or **QWEN 3** for better Brainstorming regarding Architectural designs locally. But as I love doing a lot of R AND D, my chrome has a lot of tabs opened + VS Code +  docker so my RAM is consumed so less RAM is available some time.

SO I went with QWEN2.5 with 7b