# Ollama API 
### Basic APIs that are exposed at localhost:11434 that you can use with your AI app.

## https://docs.ollama.com/api/introduction

## to Use Generate API
'''
curl http://localhost:11434/api/generate -d '{
  "model": "gemma4",
  "prompt": "Why is the sky blue?"
}'
'''


## To use embed API for embeddings

```
curl http://localhost:11434/api/embed -d '{
  "model": "embeddinggemma",
  "input": "Why is the sky blue?"
}'
```

## Generate a chat message

```
curl http://localhost:11434/api/chat -d '{
  "model": "gemma4",
  "messages": [
    {
      "role": "user",
      "content": "why is the sky blue?"
    }
  ]
}'
```