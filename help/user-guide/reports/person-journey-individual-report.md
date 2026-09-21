---
title: Relatório Individual de Jornada de Pessoa
description: Saiba mais sobre o relatório Jornada de pessoa individual no Adobe Marketo Otimizer, que mostra as métricas de conclusão, envolvimento e email de uma jornada.
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
source-git-commit: 531dce4ffe6000efa0296f0e2393423f54124ea7
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 0%
---

# Relatório Individual de Jornada de pessoa

<!-- SPHR-39120: UX plans to move the Journey activity flow tile to the top of the report. Update the tile order in this page when that ships. -->

Clique em **[!UICONTROL Exibir relatório]** para que uma jornada de pessoa viva ou encerrada veja seu desempenho, incluindo status, envolvimento, métricas de email e fluxo de atividades.

_Para exibir o relatório :_

1. Abra uma jornada de pessoas **[!UICONTROL Ao Vivo]** ou **[!UICONTROL Concluída]** na lista _[!UICONTROL jornadas de pessoas]_.
1. No cabeçalho da jornada, selecione **[!UICONTROL Exibir Relatório]**.

   ![Tela de jornada de pessoa com o botão Exibir relatório realçado no cabeçalho da jornada.](./assets/reports-person-journey-view-report.png){width="600" zoomable="yes"}

Você pode [alterar o intervalo de datas](./reports-overview.md#change-the-date-range) do relatório.

Selecione **[!UICONTROL Compartilhar]** na parte superior do relatório para baixar ou agendar uma exportação dos dados. Consulte [_Exportar um relatório_](./reports-overview.md#export-a-report) na visão geral de Relatórios.

![Relatório individual de Jornada de pessoa mostrando o status da jornada, a tendência de conclusão e os blocos de engajamento.](./assets/reports-individual-journey.png){width="700" zoomable="yes"}

## Filtros {#filters}

O escopo dos filtros de relatório é a jornada atual.

* **[!UICONTROL Nome da Jornada (Evento)]** - Predefinido para a jornada da qual você abriu o relatório.
* **[!UICONTROL Persona (Evento)]** - (_Ainda não suportado_) Filtre o relatório para pessoas que correspondam a um [perfil derivado](../audiences/personas.md#filter-by-derived-persona) específico. O padrão é [!UICONTROL Nenhum filtro].

Selecione **[!UICONTROL Redefinir tudo]** para limpar o filtro _[!UICONTROL Persona (Evento)]_ e retornar ao modo de exibição padrão.

## Status pessoal e envolvimento {#person-status-and-engagement}

Esta seção apresenta quatro blocos:

* **[!UICONTROL Status das pessoas na jornada]** - Divide as pessoas na jornada em _[!UICONTROL Concluídas]_ e _[!UICONTROL Em andamento]_ categorias, com as porcentagens correspondentes.
* **[!UICONTROL Pessoas concluídas ao longo do tempo]** - Um gráfico de linhas que controla o número de pessoas que concluíram a jornada durante o intervalo de datas selecionado.
* **[!UICONTROL Pessoas envolvidas vs. não envolvidas]** - Divide as pessoas na jornada em _[!UICONTROL Envolvidas]_ e _[!UICONTROL Não envolvidas]_ categorias, com as porcentagens correspondentes.
* **[!UICONTROL Pessoas envolvidas]** - O número total de pessoas qualificadas como envolvidas na jornada.

## Desempenho do email {#email-performance}

A tabela de [!UICONTROL Desempenho do email] mostra as métricas de entrega e envolvimento para cada email enviado na jornada. Para obter as mesmas métricas de email em todas as jornadas, consulte o [relatório de Engajamento no Email](./email-engagement-report.md).

![Tabela de desempenho de email que mostra as métricas enviadas, entregues, abertas e clicadas para um email.](./assets/reports-individual-journey-email-performance.png){width="700" zoomable="yes"}

Colunas da tabela de [!UICONTROL Desempenho do email]:

* [!UICONTROL Nome do email] - Nome do email.
* [!UICONTROL Enviado] - Número de emails enviados.
* [!UICONTROL Entregues] - Número de emails entregues.
* [!UICONTROL % Entregue] - Número de emails entregues dividido pelo número enviado.
* [!UICONTROL Aberto] - Número de vezes que os destinatários abriram o email.
* [!UICONTROL % aberto] - Número de emails abertos dividido pelo número entregue.
* [!UICONTROL Clicado] - Número de vezes que os destinatários clicaram em um link no email.
* [!UICONTROL % de cliques] - Número de emails clicados dividido pelo número entregue.

## Jornada fluxo de atividades {#journey-activity-flow}

A visualização do [!UICONTROL fluxo de atividade de Jornada] mostra o caminho que as pessoas tomam por meio da jornada, começando com a atividade _[!UICONTROL Adicionar pessoa à Jornada]_. Cada nó mostra o número de exibições de caminho para essa atividade.

![Visualização do fluxo de atividades do Jornada mostrando exibições de caminho de Adicionar pessoa ao jornada por meio da entrega de email.](./assets/reports-individual-journey-activity-flow.png){width="700" zoomable="yes"}
