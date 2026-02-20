# Overview

Ollama runs LLMs like Mistral or Llama locally.  They can be run in a docker container so models and history are isolated in the container, can be run offline, and everything can be fully deleted.

- The Ollama runtime itself (~3GB) lives inside the container image.
- The container starts as a copy of that image plus a writable layer.
- The Mistral model (~4GB) is downloaded inside the container’s writable layer.
- The container's size now includes Ollama (~3GB) + Mistral (~4GB) = ~7GB.

# Supported Models

- Mistral 7B – Efficient open-source general-purpose LLM with strong performance for its size.
- Llama 3.1 – Meta's capable, widely-used generalist LLM with a large ecosystem.
- Gemma 2 – Google's efficient multilingual model family, good for on-device/low-resource usage.
- Qwen 2.5 – Alibaba's strong multilingual and reasoning model with large context support.
- Phi-3 – Microsoft's small, cost-efficient LLM series with strong language/reasoning.
- DeepSeek Coder v2 – MoE code-specialized LLM with very strong performance on coding tasks.

# First Time
``docker run -d --name ollama ollama/ollama``

# Next Time
``docker start ollama``

# Run LLM
``docker exec -it ollama ollama run mistral``
``docker exec -it ollama ollama run llama3.1``
``docker exec -it ollama ollama run gemma2``
``docker exec -it ollama ollama run qwen2.5``
``docker exec -it ollama ollama run phi3``
``docker exec -it ollama ollama run deepseek-coder-v2``

# Stop

``docker stop ollama``

# Clear Down
``docker rm ollama``
``docker system prune -a``

# Check Volume
``docker inspect ollama``
