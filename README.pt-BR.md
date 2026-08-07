# Knowledge Work Plugins — Fork

[English](README.md) | [Português](README.pt-BR.md)

> **Aviso de fork.** Este repositório é um fork mantido de
> [anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins),
> a coleção oficial da Anthropic de plugins que transformam o Claude em um especialista para o seu
> papel, time e empresa. Ele traz os mesmos plugins, além de correções e melhorias no plugin Zoom
> incluso — veja a seção [Delta](#delta--o-que-este-fork-muda-em-relação-ao-upstream). Todo o
> crédito da coleção é do projeto upstream.

Plugins que transformam o Claude em um especialista para o seu papel, time e empresa. Feito para [Claude Cowork](https://claude.com/product/cowork), também compatível com [Claude Code](https://claude.com/product/claude-code).

## Delta — O que este fork muda em relação ao upstream

Este fork aprimora o **plugin Zoom** (`partner-built/zoom-plugin`). Em comparação com o upstream, **12 arquivos de definição de skill** (`SKILL.md`) foram alterados, de duas formas:

### 1. Correção de identificador de skill (12 skills)

O campo `name:` no frontmatter usava identificadores no formato de caminho com barra (ex.: `contact-center/android`). Nomes com barra são frágeis — podem ser interpretados como caminhos aninhados em vez de identificadores planos de skill, o que quebra o registro e o namespacing. Todos os 12 foram renomeados para identificadores planos com hífen (ex.: `contact-center-android`).

### 2. Refatoração da definição de skill (6 skills)

Seis desses arquivos também foram condensados de longos documentos de referência embutidos (97–1.019 linhas) para definições de skill focadas (41–59 linhas). As skills agora atuam como guias concisos de roteamento e decisão que apontam para os documentos de referência dedicados que acompanham o repositório (`concepts/`, `examples/`, `references/`, `troubleshooting/`). As skills carregam mais rápido, disparam de forma mais confiável e mantêm o detalhamento completo a um clique de distância.

| Skill | `name:` antes | `name:` depois | Escopo |
|---|---|---|---|
| `contact-center/android` | `contact-center/android` | `contact-center-android` | Correção de identificador |
| `contact-center/ios` | `contact-center/ios` | `contact-center-ios` | Correção de identificador |
| `contact-center/web` | `contact-center/web` | `contact-center-web` | Correção de identificador |
| `virtual-agent/android` | `virtual-agent/android` | `virtual-agent-android` | Correção de identificador |
| `virtual-agent/ios` | `virtual-agent/ios` | `virtual-agent-ios` | Correção de identificador |
| `virtual-agent/web` | `virtual-agent/web` | `virtual-agent-web` | Correção de identificador |
| `meeting-sdk/linux` | `meeting-sdk/linux` | `meeting-sdk-linux` | Correção de identificador + refatoração (429 → 59 linhas) |
| `ui-toolkit` | `ui-toolkit/web` | `ui-toolkit-web` | Correção de identificador + refatoração (555 → 45 linhas) |
| `video-sdk/linux` | `video-sdk/linux` | `video-sdk-linux` | Correção de identificador + refatoração (443 → 42 linhas) |
| `video-sdk/web` | `video-sdk/web` | `video-sdk-web` | Correção de identificador + refatoração (821 → 41 linhas) |
| `video-sdk/windows` | `video-sdk/windows` | `video-sdk-windows` | Correção de identificador + refatoração (1.019 → 45 linhas) |
| `zoom-mcp/whiteboard` | `zoom-mcp/whiteboard` | `zoom-mcp-whiteboard` | Correção de identificador + refatoração (97 → 54 linhas) |

Todas as alterações estão registradas no [histórico de commits](https://github.com/belbatera/knowledge-work-plugins/commits/main) do fork (mais recente: "Refactor zoom-mcp whiteboard skill documentation", `5113e9d`).

## Por que plugins

O Cowork permite que você defina a meta e o Claude entrega um trabalho finalizado e profissional. Os plugins permitem ir além: ensinar ao Claude como você gosta que o trabalho seja feito, quais ferramentas e dados usar, como lidar com fluxos de trabalho críticos e quais slash commands expor — para que seu time obtenha resultados melhores e mais consistentes.

Cada plugin reúne as skills, conectores, slash commands e sub-agentes de uma função específica. Prontos para uso, eles dão ao Claude um excelente ponto de partida para ajudar qualquer pessoa nessa função. O verdadeiro poder aparece quando você os personaliza para a sua empresa — suas ferramentas, sua terminologia, seus processos — para que o Claude trabalhe como se tivesse sido feito para o seu time.

## Marketplace de plugins

Estamos abrindo o código de 11 plugins construídos e inspirados em nosso próprio trabalho:

| Plugin | Como ajuda | Conectores |
|--------|------------|------------|
| **[productivity](./productivity)** | Gerencia tarefas, calendários, fluxos diários e contexto pessoal para você gastar menos tempo repetindo-se. | Slack, Notion, Asana, Linear, Jira, Monday, ClickUp, Microsoft 365 |
| **[sales](./sales)** | Pesquisa prospects, prepara calls, revisa o pipeline, redige abordagens e cria battlecards competitivos. | Slack, HubSpot, Close, Clay, ZoomInfo, Notion, Jira, Fireflies, Microsoft 365 |
| **[customer-support](./customer-support)** | Classifica tickets, redige respostas, empacota escalonamentos, pesquisa contexto do cliente e transforma problemas resolvidos em artigos de knowledge base. | Slack, Intercom, HubSpot, Guru, Jira, Notion, Microsoft 365 |
| **[product-management](./product-management)** | Escreve specs, planeja roadmaps, sintetiza pesquisa de usuários, mantém stakeholders atualizados e acompanha o cenário competitivo. | Slack, Linear, Asana, Monday, ClickUp, Jira, Notion, Figma, Amplitude, Pendo, Intercom, Fireflies |
| **[marketing](./marketing)** | Redige conteúdo, planeja campanhas, aplica o brand voice, faz briefings de concorrentes e reporta desempenho por canal. | Slack, Canva, Figma, HubSpot, Amplitude, Notion, Ahrefs, SimilarWeb, Klaviyo |
| **[legal](./legal)** | Revisa contratos, classifica NDAs, navega em compliance, avalia riscos, prepara reuniões e redige respostas padronizadas. | Slack, Box, Egnyte, Jira, Microsoft 365 |
| **[finance](./finance)** | Prepara lançamentos contábeis, concilia contas, gera demonstrações financeiras, analisa variações, gerencia fechamento e apoia auditorias. | Snowflake, Databricks, BigQuery, Slack, Microsoft 365 |
| **[data](./data)** | Consulta, visualiza e interpreta conjuntos de dados — escreve SQL, executa análise estatística, cria dashboards e valida o trabalho antes de compartilhar. | Snowflake, Databricks, BigQuery, Definite, Hex, Amplitude, Jira |
| **[enterprise-search](./enterprise-search)** | Encontra qualquer coisa em e-mail, chat, documentos e wikis — uma consulta em todas as ferramentas da empresa. | Slack, Notion, Guru, Jira, Asana, Microsoft 365 |
| **[bio-research](./bio-research)** | Conecta-se a ferramentas e bancos de dados de pesquisa pré-clínica (busca de literatura, análise genômica, priorização de alvos) para acelerar a P&D de ciências da vida em estágio inicial. | PubMed, BioRender, bioRxiv, ClinicalTrials.gov, ChEMBL, Synapse, Wiley, Owkin, Open Targets, Benchling |
| **[cowork-plugin-management](./cowork-plugin-management)** | Cria novos plugins ou personaliza os existentes para as ferramentas e fluxos de trabalho específicos da sua organização. | — |

Instale-os diretamente pelo Cowork, navegue pela coleção completa aqui no GitHub ou crie os seus.

## Começando

### Quick Start

**Cowork** — instale plugins em [claude.com/plugins](https://claude.com/plugins/).

**Claude Code** — adicione este fork como marketplace e depois instale um plugin:

```bash
# Adicione o marketplace primeiro (este fork)
claude plugin marketplace add belbatera/knowledge-work-plugins

# Depois instale um plugin específico (ex.: o plugin Zoom)
claude plugin install zoom-plugin@knowledge-work-plugins
```

Após a instalação, os plugins ativam automaticamente. As skills disparam quando relevantes e os slash commands ficam disponíveis na sua sessão (ex.: `/sales:call-prep`, `/data:write-query`).

### Passo a passo para iniciantes

1. **Instale o Claude Code** (ou use o [Claude Cowork](https://claude.com/product/cowork)) e faça login.
2. **Adicione o marketplace** deste fork:
   ```bash
   claude plugin marketplace add belbatera/knowledge-work-plugins
   ```
3. **Instale um plugin** — substitua `zoom-plugin` por qualquer nome de plugin da [tabela do marketplace](#marketplace-de-plugins):
   ```bash
   claude plugin install zoom-plugin@knowledge-work-plugins
   ```
4. **Verifique se funciona** — inicie uma nova sessão e faça uma pergunta relacionada ao plugin. As skills ativam automaticamente quando os triggers correspondem; os slash commands ficam disponíveis na sua sessão.
5. **Personalize** — edite o `.mcp.json` do plugin (conexões de ferramentas) e os arquivos de `skills/` (conhecimento de domínio) para alinhar às suas ferramentas e processos. Veja [Tornando-os seus](#tornando-os-seus).
6. **Mantenha-se atualizado** — faça pull deste repositório ou re-adicione o marketplace periodicamente para receber as correções mais recentes.

## Como os plugins funcionam

Todo plugin segue a mesma estrutura:

```
plugin-name/
├── .claude-plugin/plugin.json   # Manifest
├── .mcp.json                    # Conexões de ferramentas
├── commands/                    # Slash commands que você invoca explicitamente
└── skills/                      # Conhecimento de domínio que o Claude usa automaticamente
```

- **Skills** codificam a expertise de domínio, as melhores práticas e os fluxos passo a passo de que o Claude precisa para ajudar com qualidade. O Claude as usa automaticamente quando relevante.
- **Commands** são ações explícitas que você dispara (ex.: `/finance:reconciliation`, `/product-management:write-spec`).
- **Connectors** conectam o Claude às ferramentas externas das quais sua função depende — CRMs, gestores de projetos, data warehouses, ferramentas de design e mais — via [servidores MCP](https://modelcontextprotocol.io/).

Todos os componentes são baseados em arquivos — markdown e JSON, sem código, sem infraestrutura, sem etapas de build.

## Tornando-os seus

Esses plugins são pontos de partida genéricos. Eles se tornam muito mais úteis quando você os personaliza para como a sua empresa realmente funciona:

- **Troque os conectores** — Edite o `.mcp.json` para apontar para a sua pilha de ferramentas.
- **Adicione contexto da empresa** — Insira sua terminologia, estrutura organizacional e processos nos arquivos de skill para que o Claude entenda o seu mundo.
- **Ajuste os fluxos** — Modifique as instruções das skills para refletir como seu time realmente trabalha, e não como um manual diz.
- **Crie novos plugins** — Use o plugin `cowork-plugin-management` ou siga a estrutura acima para criar plugins para funções e fluxos ainda não cobertos.

À medida que seu time cria e compartilha plugins, o Claude se torna um especialista multifuncional. O contexto que você define é incorporado a cada interação relevante, permitindo que líderes e administradores gastem menos tempo impondo processos e mais tempo melhorando-os.

## Contribuindo

Plugins são apenas arquivos markdown. Faça um fork do repositório, faça suas alterações e envie um pull request para este repositório. Se a sua alteração for uma melhoria geral da coleção (não uma correção específica do fork), considere contribuir também para o [repositório upstream](https://github.com/anthropics/knowledge-work-plugins).

## Licença

Distribuído sob a mesma licença do projeto upstream — veja [`LICENSE`](LICENSE).
