# Ollama API 
### Basic APIs that are exposed at localhost:11434 that you can use with your AI app.

### [Ollama API Reference](https://docs.ollama.com/api/introduction)

## To Use Generate API
### Generates a response for the provided prompt
```
curl http://localhost:11434/api/generate -d '{
  "model": "gemma4",
  "prompt": "Why is the sky blue?"
}'
```


## To use embed API for embeddings
### Creates vector embeddings representing the input text

```
curl http://localhost:11434/api/embed -d '{
  "model": "embeddinggemma",
  "input": "Why is the sky blue?"
}'
```

## Generate a chat message
### Generate the next chat message in a conversation between a user and an assistant.

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