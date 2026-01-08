# AIHomeLab
Creation of a self-hosted, automated, and reproducible local AI environment

Docker: Containers all services (Ollama, a Web UI, etc.) for isolation and easy management.
Ollama: Runs the Large Language Models (LLMs) locally on your hardware, with optional GPU acceleration.
Open WebUI: A user-friendly, ChatGPT-like interface for interacting with the Ollama models through your local network. 

1. Install Docker Desktop (with GPU support) - and WSL 2 (windows subsystem for linux)
2. Install Ollama using docker
       docker pull ollama/ollama
3. Run the Ollama docker container
       docker run -d --gpus all -p 11434:11434 --name ollama ollama/ollama
5. Pull a model
       docker exec ollama ollama pull ministral-3:3b
6. Install Open WebUI by first cloning the github repo
       git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui.git
7. Run webui in Docker
       docker run -d --name webui -p 7860:8080 -v "$env:USERPROFILE\WebUI\config:/config" ghcr.io/open-webui/open-webui:main
