Agentic Runtime Security

Overview

Nowadays, many AI agents are connected to enterprise resources like databases, APIs, cloud services, and internal applications. Most of these AI agents are given permanent credentials or administrator privileges so they can perform tasks automatically. If an attacker compromises the AI through prompt injection, jailbreak attacks, stolen credentials, or other vulnerabilities, they may gain access to all enterprise resources.

This project is designed to solve that problem.

The main idea is **not to trust the AI with permanent access**. Instead, the AI should receive only the minimum permissions required to complete a specific task. Every request starts by verifying the user's identity through Okta. The AI then analyzes the user's intent using a local LLM, determines the required action, evaluates the risk, and requests temporary permissions only for that task.

The generated permissions are:

Session-bound – valid only for the current session.
Intent-bound – limited to the requested resource and action.
Time-bound – automatically revoked after a short period.

This approach follows security principles such as **Identity-First Security, Least Privilege, Zero Standing Privilege (ZSP), Just-In-Time (JIT) Authorization, and Defense in Depth.

The objective of this project is to build a secure runtime architecture for AI agents that reduces the impact of attacks like Prompt Injection, Excessive Agency, Over-Privileged AI Agents, Static Credential Exposure, and Unauthorized Resource Access.

This project uses Okta for Identity and Access Management, OAuth 2.0 and OpenID Connect (OIDC) for authentication, JWT for identity verification, n8n as the orchestration engine, Ollama with a local LLM for intent analysis, PostgreSQL as the protected resource, and Docker for the local development environment.

This is a learning and portfolio project that demonstrates how modern IAM and AI Security concepts can be combined to build a secure AI runtime instead of giving AI agents unrestricted access to enterprise systems.
