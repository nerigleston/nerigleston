<div align="center">

# Nerigleston Filho (Neri)

### Backend e IA generativa em produção

**Da ideia ao sistema no ar, sem etapa de slide.**

Consultoria pra descobrir o que vale construir, e a construção em seguida:<br/>
sistemas sob medida, IA em produção e landing pages. Escopo fechado, entregue rodando.

<a href="https://nerifilho.com.br"><img src="https://img.shields.io/badge/nerifilho.com.br-232323?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Site"/></a>
<a href="https://nerifilho.com.br/projetos"><img src="https://img.shields.io/badge/12%20projetos-0d9488?style=for-the-badge" alt="Projetos"/></a>
<a href="https://nerifilho.com.br/blog"><img src="https://img.shields.io/badge/Blog-232323?style=for-the-badge&logo=rss&logoColor=white" alt="Blog"/></a>
<a href="https://www.linkedin.com/in/nerigleston/"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge" alt="LinkedIn"/></a>
<a href="https://wa.me/5583991230146"><img src="https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" alt="WhatsApp"/></a>

</div>

---

## Sobre

Trabalho com backend e IA generativa. Quem diagnostica, escreve o código e sobe em produção sou eu: não há time por trás nem repasse para terceiros.

- Mantenho a [**Jangada AI**](https://jangada.dev.br), biblioteca open source que unifica 9 providers de LLM sob uma interface Python só
- Formado em Análise e Desenvolvimento de Sistemas, com pós em Ciência de Dados
- Presencial em João Pessoa, Campina Grande, Recife, Caruaru e Natal; remoto no resto do Brasil e no exterior

### Em número, medido em produção

| | |
|---|---|
| **4×** | mais throughput num pipeline de Open Finance depois de reescrever em Go: de 1 a 3 para 8 a 9 transações por segundo |
| **9** | providers de LLM sob a mesma API na Jangada AI |
| **3** | frentes de busca em paralelo, com reescrita automática de consulta, num RAG médico em produção na oftalmologia |

---

## Open source

### 🛶 Jangada AI

**Uma camada fina e adaptável sobre os SDKs de LLM.** Troque provider, modelo ou api_key sem reescrever o resto do código. Documentação em PT-BR, observabilidade nativa (1 linha no `.env`) e servidor MCP da própria doc.

<div>
  <img src="https://img.shields.io/pypi/v/jangada-ai?style=for-the-badge&color=0d9488&label=PyPI" alt="PyPI version"/>
  <img src="https://img.shields.io/badge/license-MIT-0d9488?style=for-the-badge" alt="MIT License"/>
  <img src="https://img.shields.io/badge/status-1.x%20SemVer-0d9488?style=for-the-badge" alt="Status"/>
</div>

```python
from jangada_ai import LLM

# troque o provider numa linha, o resto do código não muda
llm = LLM("anthropic", "claude-opus-4-8").with_fallback(
    LLM("openai", "gpt-5"),
)
resp = llm.complete("Explique {{tema}} em 2 frases.", tema="MCP")
print(resp.text, resp.cost)
```

**Providers:** Anthropic, OpenAI, Gemini, Groq, Mistral, OpenRouter, AWS Bedrock, Azure OpenAI e Vertex AI.

**Inclui:** structured output, vision, áudio, documentos (pdf/docx/csv/xlsx), tools, RAG (pgvector/Mongo + busca híbrida), retry + fallback, custo por chamada, fluxos sequenciais e orquestração em grafo (roteamento + paralelo).

**Doc no editor via MCP:** conecta a documentação da Jangada no Claude Code, Cursor ou Claude Desktop, pra o assistente codar com a API atual sem inventar assinatura de função.

[Site](https://jangada.dev.br) · [Docs](https://docs.jangada.dev.br) · [PyPI](https://pypi.org/project/jangada-ai/)

O ecossistema em volta da biblioteca:

| Produto | O que faz |
|---|---|
| [**Jangada Cloud**](https://app.mcp.jangada.dev.br) | Hospedagem de servidores MCP em Python. Função pública vira ferramenta, docstring vira descrição, type hint vira schema. Deploy pelo painel ou direto do GitHub, com versões, rollback, OAuth, logs e domínio próprio |
| [**Jangada Observability**](https://app.jangada.dev.br) | Cada chamada de LLM vira um trace com custo, tokens e latência, por organização e projeto. Latência p95, taxa de erro, alertas, datasets, experimentos e versões de prompt |

### 🐦 Bando

App nativo para macOS que roda vários agentes de código em paralelo. Cada tarefa ganha um git worktree, uma branch e uma sessão tmux com o agente escolhido: Claude Code, Codex, OpenCode, Antigravity ou qualquer CLI configurada em TOML. Troca de agente no meio da sessão levando o resumo do que já foi feito, custo por sessão e MCP cadastrado uma vez para todos. SwiftUI, sem Electron: 28 MB de app, uns 110 MB de memória com quatro sessões abertas. MIT.

[Site](https://bando.nerifilho.com.br) · [Código](https://github.com/nerigleston/bando)

### 🗄️ BaseHub

Painel para quem tem bancos no Supabase espalhados por várias contas. Junta contas e organizações num lugar só, cria e reativa projetos, roda SQL, navega nas tabelas e mantém um keep-alive diário pra o plano grátis não pausar. Tokens cifrados e registro de atividade. Versão hospedada ou self-hosted (AGPL-3.0).

[Site](https://basehub.nerifilho.com.br) · [Código](https://github.com/nerigleston/supabase-hub)

---

## Produtos e projetos no ar

| Projeto | O que é | Status | Meu papel |
|---|---|---|---|
| [**Seelo**](https://seelo.visionstds.com.br) | Emissão de NFS-e pelo Emissor Nacional: API REST com webhooks assinados e sandbox, painel multiempresa e IA que monta a nota a partir da foto de um recibo | Lista de espera | Back-end e lógica, em parceria com a Vision |
| [**Carhub**](https://carhub.visionstds.com.br) | Sistema para oficina mecânica: foto da placa acha o carro, áudio do mecânico vira orçamento, cliente aprova item por item pelo celular | No ar | Back-end e lógica, em parceria com a Vision |
| [**Nascente**](https://nascente.visionstds.com.br) | O app de João Pessoa, começando por vagas de emprego, estágio e Jovem Aprendiz por bairro | No ar | Back-end e lógica, em parceria com a Vision |
| [**Confinar**](https://confinaragro.com.br) | Gestão de confinamento bovino: mapa de trato, leitura de cocho, custo da arroba produzida e GMD por lote, com mais de 40 relatórios | No ar | Cofundador |
| [**Cronoar**](https://cronoar.com.br) | Cronometragem esportiva na PB e no RN: inscrições, agenda, resultados e área do atleta | No ar | Autoria completa, do site ao sistema |
| [**Conta Azul MCP**](https://contaazulmcp.nerifilho.com.br) | A Conta Azul dentro do Claude e do ChatGPT: login por OAuth, 26 consultas e 29 ações de escrita liberadas uma a uma e aprovadas a cada uso | No ar | Autoria completa, sobre a Jangada AI |
| [**Maria Helena Moura**](https://fgamariahelenamoura.com.br) | Site de fonoaudióloga feito para ser achado: SEO local, dados estruturados, conteúdo citável por IA e llms.txt | No ar | Trabalho para cliente |

Descrição completa de cada um em [nerifilho.com.br/projetos](https://nerifilho.com.br/projetos).

---

## Trabalhe comigo

Atendo empresas como freelance, em quatro frentes:

- [**Consultoria e diagnóstico**](https://nerifilho.com.br/consultoria-de-ia): onde automatizar, onde IA compensa e onde ela só encarece. Você sai com um plano priorizado, com esforço e custo estimados, e sem obrigação de me contratar pra construir
- [**IA em produção**](https://nerifilho.com.br/ia-em-producao): RAG com busca híbrida e resposta verificada, agentes com grafo explícito de estados, Text-to-SQL auditável. Cada etapa medida: custo por requisição, latência e taxa de acerto
- [**Sistemas sob medida**](https://nerifilho.com.br/sistemas-sob-medida): backend, API, integração entre o que você já usa, painel interno, automação de trabalho manual. Com IA ou sem, o que resolver mais barato e quebrar menos
- [**Sites e landing pages**](https://nerifilho.com.br/landing-pages): página estática, SEO técnico, Core Web Vitals, nada de terceiro pesando no carregamento

**Como funciona**

1. Você me conta o problema ou a ideia em duas linhas. Respondo em até 24h, mesmo que seja pra dizer "não é comigo"
2. Diagnóstico, depois proposta fechada: entregáveis, prazo e preço definidos antes de começar. Sem hora aberta
3. Entrego rodando: container, deploy, observabilidade e handover. O projeto acaba quando está no ar e alguém usa

Às vezes a resposta é "não precisa de IA". Quando uma integração, um script ou uma mudança no processo resolve mais barato, é isso que eu recomendo.

---

## Blog

Notas de quem está construindo, em [nerifilho.com.br/blog](https://nerifilho.com.br/blog) ([RSS](https://nerifilho.com.br/blog/feed.xml)):

- **Radar**, toda segunda: o que mudou na semana em segurança, runtimes, cloud e modelos, e o que isso exige de quem mantém sistema em produção
- [O que separa um RAG de demo de um RAG em produção](https://nerifilho.com.br/blog/rag-de-demo-e-rag-de-producao)
- [Selenium na Lambda: as vantagens, com a conta feita](https://nerifilho.com.br/blog/selenium-na-lambda)

---

## Stack

**Linguagens**

<div>
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white" alt="Go"/>
  <img src="https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript"/>
  <img src="https://img.shields.io/badge/Swift-F05138?style=for-the-badge&logo=swift&logoColor=white" alt="Swift"/>
  <img src="https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=postgresql&logoColor=white" alt="SQL"/>
</div>

**IA generativa**

<div>
  <img src="https://img.shields.io/badge/Jangada%20AI-0d9488?style=for-the-badge" alt="Jangada AI"/>
  <img src="https://img.shields.io/badge/LangGraph-1C3C3C?style=for-the-badge&logo=langchain&logoColor=white" alt="LangGraph"/>
  <img src="https://img.shields.io/badge/LangChain-1C3C3C?style=for-the-badge&logo=langchain&logoColor=white" alt="LangChain"/>
  <img src="https://img.shields.io/badge/LangSmith-2E2E2E?style=for-the-badge&logo=langchain&logoColor=white" alt="LangSmith"/>
  <img src="https://img.shields.io/badge/MCP-000000?style=for-the-badge&logo=anthropic&logoColor=white" alt="MCP"/>
  <img src="https://img.shields.io/badge/FastMCP-009688?style=for-the-badge&logo=fastapi&logoColor=white" alt="FastMCP"/>
  <img src="https://img.shields.io/badge/A2A-4285F4?style=for-the-badge&logo=google&logoColor=white" alt="A2A"/>
  <img src="https://img.shields.io/badge/Anthropic-191919?style=for-the-badge&logo=anthropic&logoColor=white" alt="Anthropic"/>
  <img src="https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white" alt="OpenAI"/>
  <img src="https://img.shields.io/badge/Gemini-8E75B2?style=for-the-badge&logo=googlegemini&logoColor=white" alt="Gemini"/>
  <img src="https://img.shields.io/badge/Groq-F55036?style=for-the-badge" alt="Groq"/>
</div>

**Backend e frontend**

<div>
  <img src="https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white" alt="FastAPI"/>
  <img src="https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white" alt="Django"/>
  <img src="https://img.shields.io/badge/Gin-008ECF?style=for-the-badge&logo=gin&logoColor=white" alt="Gin"/>
  <img src="https://img.shields.io/badge/NestJS-E0234E?style=for-the-badge&logo=nestjs&logoColor=white" alt="NestJS"/>
  <img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white" alt="Node.js"/>
  <img src="https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white" alt="Next.js"/>
  <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" alt="React"/>
  <img src="https://img.shields.io/badge/SwiftUI-0D96F6?style=for-the-badge&logo=swift&logoColor=white" alt="SwiftUI"/>
</div>

**Dados**

<div>
  <img src="https://img.shields.io/badge/PostgreSQL-336791?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL"/>
  <img src="https://img.shields.io/badge/pgvector-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="pgvector"/>
  <img src="https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white" alt="MongoDB"/>
  <img src="https://img.shields.io/badge/DynamoDB-4053D6?style=for-the-badge" alt="DynamoDB"/>
  <img src="https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white" alt="Redis"/>
  <img src="https://img.shields.io/badge/Elasticsearch-005571?style=for-the-badge&logo=elasticsearch&logoColor=white" alt="Elasticsearch"/>
  <img src="https://img.shields.io/badge/Oracle-F80000?style=for-the-badge" alt="Oracle"/>
</div>

**Infra**

<div>
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker"/>
  <img src="https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white" alt="Kubernetes"/>
  <img src="https://img.shields.io/badge/AWS-232F3E?style=for-the-badge" alt="AWS"/>
  <img src="https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white" alt="Terraform"/>
  <img src="https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white" alt="Nginx"/>
  <img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black" alt="Linux"/>
</div>

---

<div align="center">

## Tem uma ideia, ou só um problema?

Serve qualquer um dos dois: me conte em duas linhas. Respondo em até 24h dizendo se é o tipo de coisa que eu faço bem. E se não for, digo isso também.

<a href="mailto:nerifilho1256@gmail.com"><img src="https://img.shields.io/badge/nerifilho1256@gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="E-mail"/></a>
<a href="https://wa.me/5583991230146"><img src="https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" alt="WhatsApp"/></a>
<a href="https://www.linkedin.com/in/nerigleston/"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge" alt="LinkedIn"/></a>
<a href="https://nerifilho.com.br"><img src="https://img.shields.io/badge/nerifilho.com.br-232323?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Site"/></a>

</div>
