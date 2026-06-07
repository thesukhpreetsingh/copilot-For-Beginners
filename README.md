# Today I am setting up copilot locally with VS code and selective model.

## **You ask what is COPILOT?**

Microsoft Copilot is an AI-powered assistant and chatbot developed by Microsoft. Designed to boost productivity, it answers questions, summarizes documents, writes text (like emails and code), generates images, and automates repetitive tasks. It uses advanced machine learning and natural language processing to assist you.

Copilot in organization based system is already set up. It connects to a pre-configured cloud server with a menu of models built-in


So the best way to do and try everything on your local system is to - 
```
# install Copilot on VS Code through extensions.
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

## Step 0: Install Copilot On VS Code
```
> Open VS Code
> Click on extensions icon on left bar of your VS Code
> Search for Copilot. Make sure you are installing the one from the publisher named "Github"
> Restart your Copilot onece
```

## Step 1: Install the Local Model Runner/ Engine (Backend)

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

So I went with **QWEN2.5 with 7b***. I believe this should be more than enough for me for now. 

Once you do that it will show something like
```
> ollama pull qwen2.5-coder:7b           
> pulling manifest 
> pulling 60e05f210007:  13% ▕███████                       ▏ 601 MB/4.7 GB   38 MB/s   1m44s
```

once done 
```
> pulling manifest 
> pulling 60e05f210007: 100%   ████████████████████████████████████████████████████████▏4GB
> pulling 66b9ea09bd5b: 100% ▕████████████████████████████████████████████████████████▏68
> pulling 1e65450c3067: 100% ▕████████████████████████████████████████████████████████▏1.6 KB
> pulling 832dd9e00a68: 100% ▕████████████████████████████████████████████████████████▏11 KB
> pulling d9bb33f27869: 100% ▕████████████████████████████████████████████████████████▏487 B
> verifying sha256 digest 
> writing manifest 
> success 
```
## Step 3 A: Test Run your model using Ollama (interactive mode)

Run the following command on your command shell
```
ollama run qwen2.5-coder:7b
```
It will take some time to start working depending upon your system.
Once it runs, you can ask some testing questions.

### To Quit it you can run
```
ctrl + d (hold and press both the keys)

or

/bye (and then press enter)
```

Or to completely stop it
Head to your task Bar on you screen round the clock, 

**Check for `Ollama icon` => `Right Click on it` => `Press Exit`**

## Step 3 B: Now Serve it
```
Ollama server
```
It will start some processing and will host.

## Step 4: Add the model to you Copilot Settings.
* Open your VS Code
* Press and hold **`ctrl + alt + I`** to open chat
* Chat window will open to your right. Click on Auto Setting in bottom of that panel.
* Click on **`Settings icon just right to Other Models option`**. On Howering on Settings icon it shows a tool tip as *Manage other models*
* A pop up will open. Click on **`Add models`** = >  **`Select Ollama`** = > **Press Enter**
* It will show something as  **`http://localhost:11434`** => **Press Enter**
* Close the pop up.
* Click on Auto option and select your model.




##### Please Note :  I ran these command in VS Code