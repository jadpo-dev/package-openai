# Changelog

## 2.0.0

- changed package `OpenAi.v2`
- retyped type `ChatCompletionRequest`
- retyped type `EmbeddingRequest`
- retyped type `StreamedChatCompletionRequest`

Each public type checked against OpenAI's API reference for chat
completions, streamed chat completions and embeddings: every field's name,
whether it is optional, and its type match what OpenAI sends and accepts.
Message content is marked as deliberately not counted as personal data
here, because Jadpo checks what an app sends a model where the app writes
it.

A request now carries OpenAI's documented bounds, so one OpenAI would refuse
is refused before it is sent: a chat completion, streamed or not, takes at
least one message, and an embedding request takes from 1 to 2,048 inputs
(OpenAI's API reference, `messages` and `input`). OpenAI documents no most
messages for a chat completion. Narrowing what a request takes is a
breaking change, so the package is `OpenAi.v2`: an app moves to it by
changing its package; one that calls `chat_completions` or `embeddings`
itself sends no empty list and no more than 2,048 inputs.

## 1.0.0

- first release

Fills the `ai` capability through OpenAI's API: `ai.generate` as a Chat
Completion in its strict structured-output mode, `ai.stream` as a streamed
Chat Completion, and `ai.embed` through its embeddings, with each model's
context window and price as OpenAI's pages gave them on 2026-10-20.
