---
name: repo_context
description: Resumo e estrutura de diretórios do projeto Engenharia de Software com IA Aplicada. Fornece contexto global da pós-graduação.
---

# Estrutura do Repositório: Engenharia de Software com IA Aplicada

Este repositório contém material de apoio, laboratórios e projetos práticos da pós-graduação / curso sobre integrar **Inteligência Artificial** e **agentes** na rotina do engenheiro de software, com foco em arquitetura **agent-first** (MCP, skills, orquestração com LLMs).

## Entrada e convenções para IAs

- **`AGENTS.md` (raiz)**: instruções universais para agentes (Cursor, Copilot, etc.); aponta para este arquivo e para **`.agents/skills/`** como lugar de *skills* e fluxos operacionais da equipe.
- **`README.md` (raiz)**: índice humano do curso com links por aula e caminhos para cada exemplo; use quando precisar mapear **qual pasta corresponde a qual tópico** do programa.
- **Pastas paralelas `*-template` e `*-z`**: em vários módulos existem versões **template** (base para o aluno) e **`-z`** (referência / solução). Ao implementar ou corrigir código, confirme em qual variante você está trabalhando.
- **`windows/tensorflow.md`**: troubleshooting específico (ex.: instalação de `@tensorflow/tfjs-node` no Windows).

## Organização de diretórios (visão geral)

| Caminho | Conteúdo |
|--------|----------|
| **`modulo01-fundamentos-de-ia-e-llms-para-programadores/`** | Fundamentos: ML no browser, Web AI, Playwright, Context7, Ollama, OpenRouter, embeddings e RAG com Neo4j. |
| **`modulo02-integracao-apis-llms/`** | Integração com APIs de LLM: gateway de modelos, LangChain/LangGraph, apps guiados, segurança (prompt injection), RAG com grafo, análise de documentos. |
| **`modulo03-mcp-na-pratica/`** | MCP na prática: servidores com SDK oficial, consumo via LangChain, API legada como MCP, segurança, publicação npm, agentes com múltiplas ferramentas. |
| **`lives/`** | Materiais de mentorias ao vivo (ex.: `2026-02-24` — Agent Skills e MCP). |
| **`windows/`** | Notas de ambiente Windows. |
| **`embaixadores/`** | Materiais auxiliares para a comunidade (pode estar vazio). |
| **`.agents/skills/`** | *Skills* e contexto operacional para IAs da equipe (inclui este `repo_context.md`). |

## Módulo 01 — pastas de laboratório (`exemplo-*`)

Laboratórios numerados no próprio repositório (alinham com o `README.md` da raiz):

- **`exemplo-00-*`**: introdução / base de projeto.
- **`exemplo-01-ecommerce-recomendations-*`**: sistema de recomendação no navegador (várias partes `parte01`…`parte05`).
- **`exemplo-02-vencendo-qualquer-jogo/`**: *self-play* / ML em jogo (ex.: Duck Hunt JS).
- **`exemplo-03-webai01`**, **`exemplo-04-webai02-temperature-and-topK`**, **`exemplo-05-webai03-multimodal/`**: Web AI (APIs do browser, sampling, multimodal).
- **`exemplo-06-playwright-testes/`**, **`exemplo-07-playwright-navegacao/`**: automação de teste e navegação com Playwright + IA.
- **`exemplo-08-context7/`**: documentação atualizada (Context7); inclui demo **Next.js** com **Better Auth** em subpasta.
- **`exemplo-09-grafana-mcp/`**: telemetria / Grafana com MCP (estrutura com subprojeto `alumnus`).
- **`exemplo-10-ollama/`**: modelos locais com Ollama.
- **`exemplo-11-openrouter/`**: roteamento de modelos via OpenRouter.
- **`exemplo-12-embeddings-neo4j-*`**, **`exemplo-13-embeddings-neo4j-rag/`**: embeddings, Neo4j e RAG em JavaScript/TypeScript.

## Módulo 02 — laboratórios numerados

- **`01-smart-model-router-gateway`**: API **Fastify** + **OpenRouter** (`@openrouter/sdk`) como gateway de modelos.
- **`02-langchain-intro`**: introdução a **LangChain** com servidor Node.
- **`03-medical-appointment-*`**, **`04-song-highlights-*`**: fluxos guiados com LLM (template / `-z`).
- **`05-safeguard-prompt-injection-*`**: ataque/defesa de **prompt injection**, guardrails; uso de **LangGraph** e **MCP** (ex.: servidor de filesystem oficial).
- **`06-rag-neo4j-students-*`**: RAG analítico com **Neo4j** (Cypher gerado/corrigido via grafo), **LangChain** / **LangGraph**, testes e2e.
- **`07-doc-analysis`**: pipeline de Q&A sobre documentos (**multipart**, PDF, **LangGraph**).

## Módulo 03 — laboratórios numerados

- **`01-multiple-mcp-tools-*`**: agente **LangGraph** consumindo ferramentas/MCP (ex.: tendências via dados/APIs).
- **`02-google-trends-agent`**: agente focado em tendências (SerpAPI / CSV, etc., conforme o projeto).
- **`03-dev-instructions-agents`**: instruções e **definições de agentes** (ex.: Playwright) sob **`.github/agents/`**.
- **`04-skills`**: assets de apoio à aula de skills (vídeo, `refs.txt`, `skills-lock.json`); não é o mesmo diretório que **`.agents/skills/`** do repositório.
- **`05-mcps-do-zero-*`**: MCP mínimo com **`@modelcontextprotocol/sdk`** e **Zod**.
- **`06-your-legacy-api-as-mcp`**: exposição de API legada como servidor MCP (`customers-mcp-*` + API **Fastify** + **MongoDB**).
- **`07-api-security-auth-rate-limiting-*`**: endurecimento de API (**JWT**, **rate limit**, **MongoDB**).
- **`08-publishing-mcps-private-npm`**: publicação de pacotes MCP privados + mesma linha de API CRUD.
- **`09-using-mcp-with-langchain`**: monorepo de exemplo: API **Node + Fastify + MongoDB** (Docker) + app **LangGraph** que integra MCP (**`@langchain/mcp-adapters`**).

## Tecnologias e conceitos base (síntese do que o repo exercita)

- **Linguagem e runtime**: **JavaScript/TypeScript** em **Node.js** (ES modules); versões-alvo frequentemente **Node 24+** nos labs recentes (sempre conferir `engines` no `package.json` da pasta).
- **Servidores HTTP**: **Fastify 5** como padrão recorrente nas APIs de laboratório.
- **Orquestração LLM**: **LangChain**, **LangGraph** (`@langchain/langgraph`, CLI `langgraph:serve` / `@langchain/langgraph-cli`), integração **OpenAI-compatible** via **`@langchain/openai`** (muitas vezes apontando para OpenRouter ou compatível).
- **Roteamento e provedores**: **OpenRouter** (SDK dedicado no gateway; variáveis de ambiente nos demais projetos).
- **MCP**: **`@modelcontextprotocol/sdk`**, inspetor oficial (`mcp:inspect`), adaptadores **`@langchain/mcp-adapters`**, servidores de referência como **`@modelcontextprotocol/server-filesystem`** onde aplicável.
- **Dados**: **Neo4j** (`neo4j-driver`) para grafos e RAG; **MongoDB** (driver nativo) nas APIs CRUD dos módulos MCP; **Docker Compose** para subir infraestrutura local nos labs que precisam.
- **Segurança em API**: **`@fastify/jwt`**, **`@fastify/rate-limit`** nos exemplos de endurecimento.
- **Validação**: **Zod** em servidores MCP TypeScript.
- **ML no cliente**: **TensorFlow.js** / exemplos Web; em alguns RAGs locais aparecem **Transformers.js** / **`@huggingface/transformers`** ou **`@xenova/transformers`** (conferir o exemplo).
- **Automação**: **Playwright** e agentes de teste descritos em **`.github/agents/`** (módulo 03).
- **Ferramentas de produtividade (ecossistema curso)**: editores agentic (**Cursor**, **Windsurf**, **Claude Code**), modelos locais (**Ollama**, Llama, Gemma, etc.), **DeepSeek**, roteamento **OpenRouter**.
- **Conectores / ingestão de contexto**: menções a ecossistema de RAG passivo e leitura de docs (**Gitingest**, **Firecrawl**, **Jina Reader**) como referência de ferramentas — nem todos precisam estar commitados como código em cada pasta.
- **Front (pontual)**: **Next.js**, **Better Auth** no exemplo Context7.

## Ação do agente

Assuma repositório **educacional** e **agent-first**: prefira MCP, skills bem delimitadas e grafos/agents observáveis (LangGraph) em vez de monólitos opacos. Para fluxos e regras **da equipe deste repo**, siga o que estiver em **`.agents/skills/`** e em **`AGENTS.md`**. Ao dúvida sobre **qual laboratório** corresponde a um tópico, cruze com **`README.md`**.
