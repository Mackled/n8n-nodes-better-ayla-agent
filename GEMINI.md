# GEMINI.md

This document provides a comprehensive overview of the `n8n-nodes-better-ai-agent` project, designed to serve as an instructional context for AI-driven development.

## Project Overview

This project is a custom node for n8n, a workflow automation tool. The `better-ai-agent` node is an enhanced version of the default AI Agent node in n8n. It provides a more robust and feature-rich experience for building AI-powered workflows.

The key features of this node include:

*   **Improved Memory Management:** The node saves all interactions, including user messages, tool calls, and tool results, to the conversation memory. This provides a more complete context for the AI agent.
*   **Modern AI SDK Integration:** It uses the Vercel AI SDK to interact with various language models like OpenAI, Gemini, and Anthropic. This ensures better performance, reliability, and compatibility with the latest AI models.
*   **Real-time Updates:** The node can send intermediate messages to a webhook URL as they happen, allowing for real-time monitoring of the agent's progress.
*   **Drop-in Replacement:** It is designed to be a drop-in replacement for the existing AI Agent node, working seamlessly with existing language model, memory, tool, and output parser nodes.

The project consists of two main nodes:

*   `BetterAiAgent.node.ts`: The primary AI agent node that executes the AI logic.
*   `BetterAiAgentTool.node.ts`: A version of the agent that can be used as a tool by other AI agents.

## Building and Running

The project is built with TypeScript and requires Node.js and npm.

### Build

To build the project, run the following command:

```bash
npm run build
```

This command transpiles the TypeScript code into JavaScript and places it in the `dist` directory.

### Development

To watch for changes and automatically rebuild the project, run:

```bash
npm run dev
```

### Local Deployment

To deploy the node locally for testing within n8n, use the following command:

```bash
npm run deploy-local
```

This command builds the project, copies the necessary files to the `.n8n/custom` directory, and installs the production dependencies.

## Development Conventions

*   **TypeScript:** The project is written in TypeScript. All new code should be in TypeScript and follow the existing coding style.
*   **Vercel AI SDK:** The project uses the Vercel AI SDK for interacting with language models. Familiarity with this SDK is recommended for development.
*   **n8n API:** The nodes are built using the n8n Node API. The code follows the patterns and conventions of this API.
*   **Modularity:** The code is organized into modules. Utility functions are kept in `utils.ts` and `utils/chatArrayMemory.ts`.
*   **Error Handling:** The code uses `NodeOperationError` for reporting errors to the n8n workflow engine.
*   **Logging:** The node uses a custom logging implementation that can be enabled with the `verboseLogs` option.
