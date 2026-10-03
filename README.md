# 🤖 AI Ticket Management System using MCP

An AI-powered ticket management system where users can **create and manage tickets using natural language**.

The application uses **Ollama as the LLM**, **MCP Client/Server for tool communication**, and **PostgreSQL for ticket persistence**.

## 🏗️ Architecture

```text
User
  ↓
MCP Client + Ollama
  ↓
MCP Server
  ↓
Ticket Tools
  ↓
PostgreSQL
```

## ✨ Features

- Create tickets using natural language
- AI-powered tool selection using Ollama
- MCP Client and MCP Server architecture
- Ticket management through MCP tools
- PostgreSQL database persistence
- Ollama running as a Docker container

## 🔧 MCP Tools

The MCP Server exposes tools such as:

```text
create_ticket
get_ticket
update_ticket
search_tickets
```

Example:

> "Create a ticket because the payment service is returning a 500 error."

Ollama understands the request and invokes the appropriate MCP tool, which creates the ticket in PostgreSQL.

## 🛠️ Tech Stack

- **Java / Spring Boot**
- **Spring AI**
- **Model Context Protocol (MCP)**
- **Ollama**
- **PostgreSQL**
- **Docker**
- **Maven**

## 🚀 Running the Project

### Start Ollama

```bash
docker run -d \
  --name ollama \
  -p 11434:11434 \
  ollama/ollama
```

Pull your required model:

```bash
docker exec -it ollama ollama pull <model-name>
```

### Start MCP Server

```bash
cd mcp-server
mvn spring-boot:run
```

### Start MCP Client

```bash
cd mcp-client
mvn spring-boot:run
```

## 🎯 Purpose

This project demonstrates how **LLMs can interact with real-world backend functionality using MCP tools**, with the MCP Server handling the business logic and database operations.
