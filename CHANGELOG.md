# Changelog

## 1.0.1

- no change to what it offers

Each public type checked against OpenAI's API reference for chat
completions, streamed chat completions and embeddings: every field's name,
whether it is optional, and its type match what OpenAI sends and accepts.
Message content is now marked as deliberately not counted as personal data
here, because Jadpo checks what an app sends a model where the app writes
it. Nothing an app writes changes.

## 1.0.0

- first release

Fills the `ai` capability through OpenAI's API: `ai.generate` as a Chat
Completion in its strict structured-output mode, `ai.stream` as a streamed
Chat Completion, and `ai.embed` through its embeddings, with each model's
context window and price as OpenAI's pages gave them on 2026-10-20.
