# Multi-Agent Customer Support System (Amazon Bedrock)

[![AWS Bedrock](https://img.shields.io/badge/AWS-Amazon_Bedrock-orange?logo=amazonaws)](https://aws.amazon.com/bedrock/)
[![Python 3.10+](https://img.shields.io/badge/Python-3.10+-blue?logo=python)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow)](https://opensource.org/licenses/MIT)

An enterprise-grade multi-agent architecture built on **Amazon Bedrock AgentCore**. The system features a centralized **Orchestrator Agent** that dynamically routes incoming customer requests to specialized sub-agents—**Customer Support** and **Knowledge Base**—using modern Agent-to-Agent (A2A) JSON-RPC 2.0 communication over custom HTTP endpoints.

---

## 🏗️ System Architecture

```text
                               +---------------------------+
                               |     User / Frontend       |
                               +-------------+-------------+
                                             |
                                             v
                               +---------------------------+
                               |    Orchestrator Agent     |
                               | (Router / Session Context)|
                               +--------+----------+-------+
                                        |          |
                    +-------------------+          +-------------------+
                    | A2A (JSON-RPC)                                   | A2A (JSON-RPC)
                    v                                                  v
    +-------------------------------+                  +-------------------------------+
    |    Customer Support Agent     |                  |     Knowledge Base Agent      |
    |  - Order Inquiries            |                  |  - Technical Troubleshooting  |
    |  - Return Policies            |                  |  - Connectivity & Hardware    |
    |  - Product Specs              |                  |  - Step-by-Step Resolution    |
    +-------------------------------+                  +-------------------------------+
