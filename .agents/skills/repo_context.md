---
name: repo_context
description: Resumo e estrutura de diretórios do projeto Engenharia de Software com IA Aplicada. Fornece contexto global da pós-graduação.
---

# Estrutura do Repositório: Engenharia de Software com IA Aplicada

Este repositório contém o material de apoio, laboratórios e projetos práticos da pós-graduação / curso sobre como integrar Inteligência Artificial e Agentes na rotina do Engenheiro de Software.

## Organização de Diretórios
- **`modulo01-fundamentos-de-ia-e-llms-para-programadores/`**: Projetos de ML/Deep Learning diretos no browser com Node.js/TensorFlow.js (ex: redes neurais, sistemas de recomendação, algoritmos genéticos).
- **`modulo02-integracao-apis-llms/`**: Conteúdo base sobre acesso a grandes modelos e ferramentas de consumo de API.
- **`modulo03-mcp-na-pratica/`**: Implementações envolvendo o framework de Model Context Protocol (MCP) para acoplar ferramentas locais e IAs.
- **`lives/`**: Materiais criados e discutidos durantes as sessões ao vivo de mentoria. (Ex: a live de início `2026-02-24` destrincha o funcionamento de **Agent Skills** e do **MCP**).
- **`windows/`**: Dicas específicas de troubleshooting para ambiente Windows.
- **`embaixadores/`**: Materiais auxiliares para a comunidade.

## Tecnologias e Conceitos Base do Projeto
- **Para IA Generativa**: Cursor, Windsurf, Claude Code, Modelos Open-Source (usando Ollama, como LLama3, Gemma), DeepSeek, Roteamento com OpenRouter.
- **Conectores e Extratores**: Ferramentas para gerar "rag passivo" e leitura de documentações (Gitingest, Firecrawl, Jina Reader).
- **Vector DB / RAG**: Implementação de RAG com Neo4j.
- **Automação**: Uso de Playwright junto a LLMs para testes e navegação.

## Ação do Agente
As IAs atuando neste diretório devem sempre assumir que este é um repositório focado em educar e montar arquiteturas "agent-first". Sempre proponha soluções modernas usando a arquitetura de "skills" conforme descrito nas sessões ao vivo.
