---
title: Habilidades dos colegas de trabalho
description: Revise as habilidades do colaborador no Marketo Otimizer — fluxos de trabalho empacotados para programas, jornadas, públicos, pontuação, conteúdo e otimização de tempo de envio.
source-git-commit: 75b481faf0d66210329f95c8afabdfa59e7bcb79
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 7%

---

# Habilidades de colega de trabalho

Uma _habilidade_ é um fluxo de trabalho empacotado que o agente sabe executar — os blocos fundamentais por trás das solicitações de menu `/` e em linguagem natural. Cada habilidade contém instruções passo a passo e as ferramentas específicas necessárias para um trabalho (por exemplo, &quot;publicar uma jornada&quot;, &quot;comparar duas listas de pessoas&quot;, &quot;criar um modelo de pontuação&quot;).

>[!NOTE]
>
>Cada habilidade é classificada de acordo com a habilidade sofrer mutação no estado [!DNL Marketo Optimizer] ou [!DNL Marketo Engage] (**Gravação**), somente consultas/análises/gerações (**Leitura**) ou com funções de consulta + mutação iguais (**Leitura+Gravação**).

## Programas e planejamento {#programs-planning}

| Habilidade | O que faz | Acesso | Superfície do produto | Impacto / fluxo de dados |
|---|---|---|---|---|
| `falco-program-creation` | Criação completa do programa [!DNL Marketo Optimizer] — programa, subpastas, tokens, listas, jornadas. | Gravar | [!DNL Marketo Optimizer] | Leituras + gravações [!DNL Marketo Optimizer]. Consulte _[Criar um programa a partir de um resumo](./program-from-brief.md)_. |
| `adapt-program` | Gerar histórias de migração dos programas [!DNL Marketo Engage] para a adaptação [!DNL Marketo Optimizer]. | Ler | [!DNL Marketo Optimizer] | Lê [!DNL Marketo Engage], escreve [!DNL Marketo Optimizer] |
| `folder-creation` | Criar pastas organizacionais na árvore de ativos. | Gravar | [!DNL Marketo Optimizer] | Leituras + gravações [!DNL Marketo Optimizer] |
| `program-creation` *(Programas de Compilação)* | Criar programas do Marketo a partir de um resumo da campanha. | Gravar | [!DNL Marketo Engage] | Leituras + gravações [!DNL Marketo Engage] |
| `program-planning` *(Campanhas de Plano)* | Transforme os resumos em documentos de configuração/implementação. | Ler | [!DNL Marketo Engage] | Lê [!DNL Marketo Engage] |
| `program-qa` *(Validar Programas)* | Validar/auditar programas (somente regras, plano de teste ou resumo). | Ler | [!DNL Marketo Engage] | Lê [!DNL Marketo Engage] |

## Jornadas {#journeys}

| Habilidade | O que faz | Acesso | Produto | Infraestrutura (fluxo de dados) |
|---|---|---|---|---|
| `journey-creation` | Crie e edite jornadas de pessoas a partir do idioma natural. | Gravar | [!DNL Marketo Optimizer] | Leituras + gravações [!DNL Marketo Optimizer] |
| `journey-edit-dates` | Alterar a data de início/término de uma jornada sem publicar. | Gravar | [!DNL Marketo Optimizer] | Leituras + gravações [!DNL Marketo Optimizer] |
| `journey-publish` | Publicar/iniciar/agendar jornadas de pessoas. | Gravar | [!DNL Marketo Optimizer] | Leituras + gravações [!DNL Marketo Optimizer] |
| `journey-stop` | Interromper, fechar, parar, parar ou matar jornadas. | Gravar | [!DNL Marketo Optimizer] | Leituras + gravações [!DNL Marketo Optimizer] |
| `journey-reentry` | Configurar reentrada: permitir/não permitir, lista suspensa, máximo de entradas. | Gravar | [!DNL Marketo Optimizer] | Leituras + gravações [!DNL Marketo Optimizer] |
| `journey-trafficcontrol` | Execute uma simulação de controle de tráfego mostrando o roteamento de perfis. | Ler | [!DNL Marketo Optimizer] | Leituras [!DNL Marketo Optimizer] (simulação) |
| `journey-observability` | Progressão de depuração/monitor — caminhos, sincronização, divisões, paralisações e ressonância. | Ler | [!DNL Marketo Optimizer] | Lê [!DNL Marketo Optimizer] + [!DNL Marketo Engage] (verificação da lista estática) |

## Públicos e pessoas {#audiences-people}

| Habilidade | O que faz | Acesso | Produto | Infraestrutura (fluxo de dados) |
|---|---|---|---|---|
| `audience-creation` | Adapte uma lista inteligente [!DNL Marketo Engage], crie uma lista de pessoas ou adicione/atualize regras. | Gravar | [!DNL Marketo Optimizer] | Lê [!DNL Marketo Engage] + lê/grava [!DNL Marketo Optimizer].  Consulte _[Criar públicos-alvo para programas](./audience-creation.md)_. |
| `people-list-comparison` | Comparar duas listas de pessoas e mostrar membros sobrepostos. | Ler | [!DNL Marketo Optimizer] | Lê [!DNL Marketo Optimizer] |
| `import-leads` | Inspecione a qualidade dos dados de CSV e confirme as importações para [!DNL Marketo Engage]. | Leitura+Gravação | Ambos | Leituras + gravações [!DNL Marketo Engage] |
| `lead-investigation` *(Investigar Clientes Potenciais)* | Investigar a atividade, a pontuação, a qualificação e o ciclo de vida de um lead. | Ler | [!DNL Marketo Engage] | Lê [!DNL Marketo Engage] |

## Conteúdo e canais {#content-channels}

| Habilidade | O que faz | Acesso | Produto | Infraestrutura (fluxo de dados) |
|---|---|---|---|---|
| `content-personalization` | Procurar/visualizar modelos e editar conteúdo/gerar variantes. | Leitura+Gravação | [!DNL Marketo Optimizer] | Leituras + gravações [!DNL Marketo Optimizer]. Consulte _[Personalizar conteúdo de email por persona](./personalize-content.md)_. |
| `asset-tokens` | CRUD de token completo em programas/pastas/jornadas. | Leitura+Gravação | [!DNL Marketo Optimizer] | Leituras + gravações [!DNL Marketo Optimizer] |
| `fcs-channels` | Pesquisas de canal e CRUD + publicar/parar/excluir. | Leitura+Gravação | [!DNL Marketo Optimizer] | Leituras + gravações [!DNL Marketo Optimizer] |

## Pontuação e sinais {#scoring-signals}

| Habilidade | O que faz | Acesso | Produto | Infraestrutura (fluxo de dados) |
|---|---|---|---|---|
| `scoring-studio` | Liste/obtenha modelos de pontuação e crie/publique-os. | Leitura+Gravação | [!DNL Marketo Optimizer] | Lê + grava [!DNL Marketo Optimizer] (serviço de pontuação); lê [!DNL Marketo Engage] campos de cliente potencial/tipos de atividade. Consulte _[Criar modelos de pontuação personalizados](./lead-scoring-model.md)_. |
| `engagementconfiguration` | Mostrar configuração de envolvimento e editar/atualizar pesos. | Leitura+Gravação | [!DNL Marketo Optimizer] | Leituras + gravações [!DNL Marketo Optimizer] |
| `intentconfiguration` | Mostrar configuração de intenção e definir/atualizar pesos. | Leitura+Gravação | [!DNL Marketo Optimizer] | Leituras + gravações [!DNL Marketo Optimizer] |
| `intent-query` | Pontuações de intenção de consulta e explicação por pessoa/segmento/lista. | Ler | [!DNL Marketo Optimizer] | Lê [!DNL Marketo Optimizer] |

## Otimização do horário de envio {#sto}

| Habilidade | O que faz | Acesso | Produto | Infraestrutura (fluxo de dados) |
|---|---|---|---|---|
| `send-time-optimization` | Verifique o status STO e ative/desative em um nó de email. | Leitura+Gravação | [!DNL Marketo Optimizer] | Leituras + gravações [!DNL Marketo Optimizer] |
| `send-time-report` | Buscar/exibir o relatório de desempenho STO. | Ler | [!DNL Marketo Optimizer] | Lê [!DNL Marketo Optimizer] |

## Conhecimento {#knowledge}

| Habilidade | O que faz | Acesso | Produto | Infraestrutura (fluxo de dados) |
|---|---|---|---|---|
| `product-knowledge` | Responda às perguntas de instrução/conceito da documentação do [!DNL Marketo Optimizer] no Experience League. | Ler | Ambos | Lê documentos externos — nenhum dado do produto |

## Cross-backend {#cross-backend}

Essas habilidades abrangem mais de um back-end:

- **`adapt-program`** — `gather_program_assets` lê [!DNL Marketo Engage] (`get_program`, `get_smart_campaign`, `list_emails`) e grava via `falcomcp_create_journey` — back-end clássico.
- **`audience-creation`** — lê [!DNL Marketo Engage] listas inteligentes (`get_smart_list` / `get_smart_campaign`) e grava [!DNL Marketo Optimizer] listas de pessoas.
- **`journey-observability`** — [!DNL Marketo Optimizer] leituras mais `check_lead_in_marketo_static_list` [!DNL Marketo Engage] leituras.
- **`scoring-studio`** — lê [!DNL Marketo Engage] campos de cliente potencial/tipos de atividade junto com o serviço de pontuação [!DNL Marketo Optimizer].

Todas as ferramentas `falco-mcp_*` e jornada/token/scoring/STO/FCS atingem [!DNL Marketo Optimizer] serviços; ferramentas CSV/programa/lead atingem [!DNL Marketo Engage].

