---
title: Habilidades dos colegas de trabalho
description: Revise as habilidades do colaborador no Marketo Optimizer para jornadas, públicos, programas, conteúdo, análises e decisões de IA. Saiba o que cada habilidade pode fazer por você.
autotag-review: '2026-09-22T14:02:17.516Z'
TQID: 'https://experienceleague.adobe.com/nNFB9UEghfqVvnBrNtTDnpnLUKKKMAU2nY1Pqt0KkUQ'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
    internal-label: Chat Interface
subfeature_v2:
  - id: b9e5c7f3-be30-563c-9e41-cc8ea76e2fee
    internal-label: Skills
topic_v2:
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
    internal-label: Artificial intelligence
source-git-commit: 5334f0f5d9d958ea47b055b067a7308950352e9c
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 4%
---

# Habilidades de colega de trabalho

Uma _habilidade_ é um fluxo de trabalho empacotado que o Co-worker pode executar. As habilidades são os componentes por trás das solicitações do menu `/` e de linguagem natural. Cada habilidade contém instruções passo a passo e as ferramentas específicas necessárias para uma tarefa, como publicar uma jornada, comparar duas listas de pessoas ou criar um modelo de pontuação.

A classificação de cada habilidade reflete o tipo de ação que ela executa:

* _Pesquisar_ habilidades para pesquisar ou listar registros existentes.
* _Analisar_ habilidades para revisar, comparar ou relatar dados sem alterá-los.
* _Exibir_ habilidades exibem um relatório ou métrica somente leitura.
* _Editar_ habilidades altera as configurações ou o conteúdo de um objeto existente.
* _Criar_ habilidades cria um novo objeto.

## Jornadas {#journeys}

Essas habilidades criam, publicam, depuram e gerenciam jornadas de pessoas.

| Habilidade | O que faz | Tipo |
| --- | --- | --- |
| **Observabilidade da Jornada** | Depurar e monitorar o movimento da pessoa por meio de uma jornada, incluindo caminhos, sincronização, divisões, paralisações e tempo de permanência. Consulte _[Depurar e monitorar a progressão da jornada](./journey-observability.md)_. | Analisar |
| **Controle de tráfego de Jornada** | Simular como os perfis são distribuídos em todas as jornadas ativas. | Analisar |
| **Publicar Jornada** | Publicar, iniciar ou agendar uma jornada, incluindo modo de início, datas e confirmação. | Editar |
| **Parada da Jornada** | Interrompa uma jornada em execução para pará-la imediatamente ou feche-a para reduzi-la normalmente. | Editar |
| **Jornada datas de edição** | Altere a data de início ou término em um rascunho, agendado ou jornada em tempo real sem publicá-la novamente. | Editar |
| **Reentrada de Jornada** | Defina as configurações de reentrada para uma jornada, incluindo se a reentrada é permitida, o atraso de resfriamento e a contagem máxima de entradas. | Editar |
| **Criação de Jornada** | Crie e edite jornadas de pessoas usando solicitações em linguagem natural. | Criar |
| **Webinar para o Jornada** | Configure uma jornada promocional antes de um webinário e uma jornada de acompanhamento depois dele. | Criar |

## Listas de público-alvo e pessoas {#audience-people-lists}

Essas habilidades criam e gerenciam listas de pessoas e definições de público-alvo.

| Habilidade | O que faz | Tipo |
| --- | --- | --- |
| **Procurar Membros da Lista Dinâmica** | Procurar e filtrar os membros de uma lista dinâmica ou estática de pessoas. | Pesquisar |
| **Comparação da Lista de Pessoas** | Comparar duas listas de pessoas e mostrar membros sobrepostos. | Analisar |
| **Remover da Lista Estática** | Remova membros que correspondem a critérios de linguagem natural de uma lista estática. | Editar |
| **Criação de público-alvo** | Adapte uma lista inteligente [!DNL Marketo Engage], crie uma lista de pessoas, ou adicione ou atualize suas regras. Consulte _[Criar públicos-alvo para programas](./audience-creation.md)_. | Criar |

## Programas, pastas e canais {#programs-folders-channels}

Essas habilidades gerenciam a estrutura do programa, os tokens e a configuração do canal.

| Habilidade | O que faz | Tipo |
| --- | --- | --- |
| **Criar programa** | Criar programas a partir de um resumo da campanha. Consulte _[Criar um programa a partir de um resumo](./program-from-brief.md)_. | Analisar |
| **Adaptar Programa** | Gerar histórias de migração dos programas [!DNL Marketo Engage] para a adaptação [!DNL Marketo Optimizer]. | Analisar |
| **Tokens de ativos** | Crie e gerencie valores de `{{my.token}}` em programas, pastas e jornadas. | Editar |
| **Canais FCS** | Criar, publicar, interromper e clonar canais no Serviço de canais, incluindo esquemas XDM e provisionamento. | Editar |
| **Criação de pasta** | Criar pastas organizacionais na árvore de ativos. | Criar |
| **Campanha integrada do WhatsApp** | Crie e publique uma campanha embutida do [!DNL WhatsApp] em um nó do jornada. | Criar |
| **Criação de programa de marketing** | Crie um programa completo, incluindo subpastas, tokens, listas de pessoas e jornadas. | Criar |
| **Criação de programa e lote de Jornadas** | Crie vários pares de programas e jornadas em uma única solicitação em lote. | Criar |

## Email e páginas de destino {#email-landing-pages}

Essas habilidades criam e gerenciam emails, formulários e landing pages.

| Habilidade | O que faz | Tipo |
| --- | --- | --- |
| **Listar Forms** | Listar formulários e exibir seus detalhes e campos. | Pesquisar |
| **Listar páginas de aterrissagem** | Listar páginas de aterrissagem, exibir seus detalhes e gerenciar seu estado de rascunho ou publicado. | Pesquisar |
| **Auditoria de email** | Auditoria de um email em relação ao grupo de destino, incluindo inferência pessoal e uma breve análise de seção por seção. | Analisar |
| **Criação de email** | Criar ou atualizar um nó de email do jornada, incluindo composição de um resumo ou PDF, vinculação a um nó e gravação de conteúdo. | Editar |
| **Criação de formulário** | Crie ou atualize um formulário de captura de cliente potencial independente, publique-o e, opcionalmente, incorpore-o em uma página de aterrissagem. | Criar |
| **Criação da página de aterrissagem** | Crie ou atualize uma landing page a partir de um resumo, incluindo planejamento de conteúdo, seleção de modelo, preenchimento de slots e adição de um formulário, depois publique-o. Anexe também uma landing page publicada como um link do call-to-action em um email. | Criar |
| **Verificação de Renderização de Email** | Verifique se há problemas de renderização no email [!DNL Microsoft Outlook] e corrija automaticamente o que for possível. | Editar |

## Personalização de conteúdo {#content-personalization}

Essa habilidade navega em modelos e personaliza o conteúdo de email para diferentes personalidades.

| Habilidade | O que faz | Tipo |
| --- | --- | --- |
| **Personalization de conteúdo** | Procure e visualize modelos, em seguida edite o conteúdo ou gere variantes. Consulte _[Personalizar conteúdo de email por persona](./personalize-content.md)_. | Criar |

## Analytics e otimização {#analytics-optimization}

Essas habilidades relatam o desempenho e configuram modelos de otimização e pontuação de tempo de envio.

| Habilidade | O que faz | Tipo |
| --- | --- | --- |
| **Análise de Superfície** | Gerar relatórios de análise a partir de solicitações em linguagem natural, abordando tendências de atividades, desempenho de email, dados de clientes potenciais e de contas, segmento e associação de listas, além de métricas de jornada. Os dados do relatório são atualizados a cada duas horas. Consulte _[Gerar relatórios de análise](./surface-analytics.md)_. | Analisar |
| **Enviar Relatório de Hora** | Exiba o relatório de desempenho de otimização de tempo de envio (STO) no nível da jornada ou para um nó de email individual. | Analisar |
| **Simulação de STO de email** | Pré-visualize o tempo de envio previsto, a qualidade do público-alvo e o mapa de calor de engajamento de um nó de email antes de habilitar o STO. | Analisar |
| **Otimização de Tempo de Envio** | Ative ou desative o STO em um nó de email do jornada. | Editar |
| **Configuração do compromisso** | Mostrar e editar os pesos da atividade para o modelo de pontuação de engajamento da pessoa. | Editar |
| **Estúdio de Pontuação** | Liste e visualize modelos de pontuação e, em seguida, crie e publique novos. Consulte _[Criar modelos de pontuação personalizados](./lead-scoring-model.md)_. | Criar |

## Decisão e intenção de IA {#ai-decisioning-intent}

Essas habilidades avaliam a prontidão dos dados para a decisão de IA e configuram a pontuação de intenção.

| Habilidade | O que faz | Tipo |
| --- | --- | --- |
| **Integridade da Decisão de IA** | Relate se os dados de uma organização estão prontos para a tomada de decisões sobre IA, incluindo disponibilidade de clientes potenciais, distribuição pessoal, riqueza da história e intenção. | Analisar |
| **Analisar intenção** | Consulte e valide a classificação de intenção no nível do lead, as tendências e a taxonomia de produtos e palavras-chave. | Analisar |
| **Configuração de intenção** | Mostrar e editar os pesos da atividade para o modelo de pontuação de intenção de pessoa. | Editar |

## Gerenciamento de conhecimentos e habilidades {#knowledge-skill-management}

Essas habilidades respondem a perguntas sobre produtos e permitem que você crie novas habilidades personalizadas.

| Habilidade | O que faz | Tipo |
| --- | --- | --- |
| **Conhecimento do Produto** | Responda as perguntas de instrução e conceituais usando a documentação do [!DNL Marketo Optimizer] publicada no Experience League. | Pesquisar |
| **Criação de habilidades** | Crie, teste e refine novas habilidades personalizadas. | Criar |
