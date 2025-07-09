---
title: Local Subtitle Generation and Translation with Pot Player + Ollama
categories: 03-Linux
---


## Install Ollama

Install with one command:

```shell
curl -fsSL https://ollama.com/install.sh | sh
```

or Manual Install:
```shell
curl -L https://ollama.com/download/ollama-linux-amd64.tgz -o ollama-linux-amd64.tgz
sudo tar -C /usr -xzf ollama-linux-amd64.tgz
```

### Run Ollama

```shell
ollama serve
```

In another terminal, verify that Ollama is running:

```shell
ollama -v
```

### Deploy local model

Search Models on: https://ollama.com/search

Download model with command in another terminal, i.e:

```
ollama run qwen2.5
```