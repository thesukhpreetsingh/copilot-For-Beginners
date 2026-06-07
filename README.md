# Today I am setting up copilot locally.

You ask what is COPILOT?
Microsoft Copilot is an AI-powered assistant and chatbot developed by Microsoft. Designed to boost productivity, it answers questions, summarizes documents, writes text (like emails and code), generates images, and automates repetitive tasks. It uses advanced machine learning and natural language processing to assist you.

Copilot in organization based system is already set up. It connects to a pre-configured cloud server with a menu of models built-in


So the best way to do and try everything on your local system is to
- use and install any open-weights or open-source AI model locally in Visual Studio Code. Because the models run entirely on your computer's hardware, your usage is 100% free and unlimited, with no monthly prompt quotas or credit limits.

To do this, you will need to install a local AI extension in VS Code and a local model runner on your machine.Popular Local Models You Can InstallThe best model for your setup depends on your computer's RAM and graphics card (VRAM).
* Qwen2.5-Coder (1.5B, 7B, or 32B): Currently considered the gold standard for local coding. 
    The 7B version strikes the best balance between speed and logic for most modern laptops.
* DeepSeek-Coder-V2 (16B or 236B): Highly advanced for complex coding tasks, but requires a powerful machine with a lot of VRAM to run efficiently.
* Llama 3.1 or Llama 3.3 (8B or 70B): Meta's general-purpose models, which are excellent for software architecture explanations, documentation, and
    debugging.
* Codellama (7B or 13B): An older but stable code-focused model from Meta.
* Phi-4 or Phi-3.5-mini (3.8B): Microsoft’s lightweight models. They are incredibly fast and ideal for older computers or laptops without
    dedicated graphics cards.

run following command in command shell on windows
irm https://ollama.com/install.ps1 | iex