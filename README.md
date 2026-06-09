# Setting up copilot locally with VS code and selective model.

## **You ask what is COPILOT?**

GitHub Copilot is an AI coding assistant developed by GitHub in collaboration with OpenAI and now supports multiple model providers. Designed to boost productivity, it answers questions, summarizes documents, writes text (like emails and code), generates images, and automates repetitive tasks. It uses advanced machine learning and natural language processing to assist you.

Copilot in organization based system is already set up. It connects to a pre-configured cloud server with a menu of models built-in


So the best way to do and try everything on your local system is to - 
```
# Install Github Copilot on VS Code through extensions.
# Use and install any open-weights or open-source AI model locally in Visual Studio Code.
# Because the models run entirely on your computer's hardware, your usage is 100% free and unlimited.
# So Running local models through Ollama does not incur API costs.
# However, it consumes your own CPU, GPU, RAM, storage and electricity.
# with no monthly prompt quotas or credit limits.
```

To do this, you will need to install a local AI extension in VS Code and a local model runner on your machine.Popular Local Models You Can Install for your setup depends on your computer's RAM and graphics card (VRAM).
* **`Qwen2.5-Coder (1.5B, 7B, or 32B):`** _Qwen2.5-Coder is one of the strongest open-weight coding models available locally._

* **`DeepSeek-Coder-V2 (16B or 236B):`** _Highly advanced for complex coding tasks, but requires a powerful machine with a lot of VRAM to run efficiently._

* **`Llama 3.1 or Llama 3.3 (8B or 70B):`** _Meta's general-purpose models, which are excellent for software architecture explanations, documentation, and debugging._

* **`Codellama (7B or 13B):`** _An older but stable code-focused model from Meta._
* **`Phi-4 or Phi-3.5-mini (3.8B):`** _Microsoft’s lightweight models. They are incredibly fast and ideal for older computers or laptops without dedicated graphics cards._

## But before We dive into further steps, let's understand __`Copilot vs Ollama vs Continue`__
| Tool  | Purpose | Runs Models? |Coding Focus?
| ------------- |:-------------:|:-------------:|:-------------:|
|Github Copilot| AI Coding Assistant inside VS Code| No | Yes
|Microsoft Copilot| General AI Assistant Like ChatGPT| No | Partial 
|Continue | VS Code extension (Github Copilot also available as VS extension)| No | Yes
|Ollama| Model Runner | Yes | No|
|Qwen/ Lama/ Gemma/ Phi|Actual AI Models|Runs by model Runners|Depends

## Basic Architecture
```
VS Code (IDE)
   |
GitHub Copilot / Continue (IDE Extensions)
   |
Ollama (Model Runner)
   |
Qwen / Llama / Gemma / Phi (Models)
```
##### Now that we understand some basics and a bit about the architecture/ workflow lets proceed.


## _**To download and run these models on your hard drive, you need a background engine. The easiest and most popular choice is Ollama**_

## Step 0: Install Copilot On VS Code
```
> Open VS Code
> Click on extensions icon on left bar of your VS Code
> Search for Copilot. Make sure you are installing the one from the publisher named "Github"
> Restart your Copilot once
```

## Step 1: Install the Local Model Runner/ Engine (Backend)

Download and install Ollama. Open your computer's Terminal (macOS/Linux) or Command Prompt (Windows).
Run the following command.
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
##### Here B stands for B stands for Billion Parameters.
For example:
7B = 7 Billion Parameters
14B = 14 Billion Parameters
32B = 32 Billion Parameters 

## Step 2: Tell your computer to download the models
Run the following caommand on command shell
```
ollama pull qwen2.5-coder:7b
```
* Choose the model respect to your needs. Use ChatGPT to reason with.
* Share your hardware specifications to ChatGPT.
* Purpose you want to use for like **`I do coding and a lot of brainstorming`** so I was recommended to use **QWEN 2.5**  (7B or 14B version) or **QWEN 3** for better Brainstorming regarding Architectural designs locally. But as I love doing a lot of R AND D, my chrome has a lot of tabs opened + VS Code +  docker so my RAM is consumed so less RAM is available some time.

So I went with **Qwen2.5-Coder 7B***. I believe this should be more than enough for me for now. 

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

### Some Open models which you can choose from, with their purpose.
|Use Case |Recommended Model/ How you can choose models|
|:------|:------|
|Qwen3	|   Coding + reasoning|
|Qwen2.5-Coder |Coding |
|Gemma 3 |Lightweight assistant |
|Llama 3.3 |General purpose And RAG|
|Phi-4 | Small laptops- Match and Logics |
|DeepSeek R1 |Reasoning|
|Mistral Small | Fast local inference|
##### Note: These are popular community choices at the time of writing. And as you know AI Space evolves rapidly so feel free to refer to any models of your choice at the time of implementing or experimenting.

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
Head to your task Bar on your screen round the clock, 

**Check for `Ollama icon` => `Right Click on it` => `Press Exit`**

## Step 3 B: Now Serve it / On Wndows it directly starts usually. If not use following command
```
Ollama server
```
It will start after some processing. Ensure the Ollama service is running.
If needed, start Ollama from the system tray or launch it manually. like shared above.

## Step 4: Add the model to your Copilot Settings.
* Open your VS Code
* Press and hold **`ctrl + alt + I`** to open chat
* Chat window will open to your right. Click on Auto Setting in bottom of that panel.
* Click on **`Settings icon just right to Other Models option`**. On Hovering on Settings icon it shows a tool tip as *Manage other models*
* A pop up will open. Click on **`Add models`** = >  **`Select Ollama`** = > **Press Enter**
* It will show something as  **`http://localhost:11434`** => **Press Enter**
* Close the pop up.
* Click on Auto option and select your model.



## Notes
##### Please Note :  I ran these command in VS Code Terminal

### Links you can follow to learn more
* To search for different models and to search through them [Ollama](https://ollama.com/search?q=qwen)
* Ollama Git hub repository = > [Ollama Github](https://github.com/ollama/ollama)
* Youtube Tutorial to [Download Ollama and use a model with it](https://www.youtube.com/watch?v=z7fhyKBAfzE)


##### There can be multiple alternatives to both the models and Code helping tools and agents. Like we can use Copilot or Continue (Continue is the actual name) extension with VS Code or any other IDE.


### Important Note
* I switched to [QWEN Model 3.5:9b.](https://ollama.com/library/qwen3.5). I found it to be better. Do suggest if you found something better.
* I had to increase the context size of my Ollama. To do so Open ollama GUI Client **=>** `Go to Settings` **=>** Scroll to bottom and look for **`Context Length Settings`**. 
```
You Ask what Context Length is ?
Context Length determines how much information the model can remember within a conversation.
Larger context allows:
- Larger code files
- Longer chats
- Bigger documentation

Increasing it may increase RAM usage.
```
* Change it to your preference. I choose it to be 64K.
* Always compare the latest benchmarks, hardware requirements, and your specific use case before choosing a model.
* Ollama and the models you choose runs using your own systems hardware.
* Many popular AI models are open-weight but not fully open-source.