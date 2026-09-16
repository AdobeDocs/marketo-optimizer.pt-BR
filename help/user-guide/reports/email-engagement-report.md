---
title: Relatório de engajamento no email
description: Saiba mais sobre o relatório Envolvimento de email no Adobe Marketo Otimizer, que mostra as métricas de capacidade de entrega e engajamento de email por email e jornada.
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
source-git-commit: 8c47a9c69c32ba0a37ba2efadb6ad4c1b796c21d
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%
---

# Relatório de engajamento com o email

<!-- SPHR-39569: content drafted, but hide: true and hide-from-toc stay until eng confirms this shipped to production. Filter by Program, Filter by Audience, and the program data point from SPHR-32511 are not documented here pending delivery-state confirmation. -->

Use o relatório [!UICONTROL Envolvimento de email] para analisar a capacidade de entrega de emails e o desempenho de engajamento em sua instância, detalhado por email e jornada.

_Para exibir o relatório :_

1. Na navegação à esquerda, selecione **[!UICONTROL Relatórios]**.
1. Clique no ícone _Lista_ ( ![Ícone Lista](../assets/do-not-localize/icon-table-of-contents.svg) ) e selecione **[!UICONTROL Envolvimento de email]** no painel _[!UICONTROL Índice]_.

![Relatório de Envolvimento de Email com o Nome da Jornada e os filtros Persona, um intervalo de datas dos Últimos 30 dias e uma tabela de métricas de atividade de email.](./assets/reports-email-engagement.png){width="700" zoomable="yes"}

Você pode [alterar o intervalo de datas](./reports-overview.md#change-the-date-range) usando o mesmo seletor de intervalo de datas disponível em outras seções de relatório.

Selecione **[!UICONTROL Compartilhar]** na parte superior do relatório para baixar ou agendar uma exportação de todos os dados do relatório. Consulte [_Exportar um relatório_](./reports-overview.md#export-a-report) na visão geral de Relatórios.

## Tabela de relatório {#report-table}

O relatório [!UICONTROL Envolvimento de email] mostra uma linha para cada email, com as seguintes dimensões de linha.

* **[!UICONTROL Nome do email]** - O nome do email.
* **[!UICONTROL Nome da Jornada]** - O nome da jornada que enviou o email.

Colunas de métrica estão agrupadas em **[!UICONTROL Atividades de email]**.

| Coluna | Descrição |
| --- | --- |
| [!UICONTROL Enviado] | Número de emails enviados. |
| [!UICONTROL Entregue] | Número de emails entregues. |
| [!UICONTROL % Entregue] | Porcentagem de emails enviados que foram entregues. |
| [!UICONTROL Devolvido(s) Fortemente] | Número de emails que falharam permanentemente na entrega. |
| [!UICONTROL Devolvido(S) Temporariamente] | Número de emails que falharam temporariamente na entrega. |
| [!UICONTROL Aberto] | Número de vezes que os destinatários abriram o email. |
| [!UICONTROL % Aberto] | Porcentagem de emails entregues que foram abertos. |
| [!UICONTROL Clicado] | Número de vezes que os recipients clicaram em um link no email. |
| [!UICONTROL % de cliques] | Porcentagem de emails entregues que receberam um clique. |
| [!UICONTROL Clique para Abrir Proporção] | Porcentagem de emails abertos que receberam um clique. |
| [!UICONTROL Cancelamento de assinatura] | Número de destinatários que cancelaram a inscrição no email. |
| [!UICONTROL % cancelado(s)] | Porcentagem de emails entregues que resultaram em um cancelamento de inscrição. |

<!--

## Filters {#filters}

Use filters to narrow the report to a specific journey, persona, or date range. Select **[!UICONTROL Reset all]** to clear every filter and return to the default view.

* **[!UICONTROL Journey Name (Event)]** - Filter by the journey that sent the email. Default is [!UICONTROL No filter].
* **[!UICONTROL Persona (Event)]** - Filter by the persona associated with the email. Default is [!UICONTROL No filter].
* **[!UICONTROL Date range]** - Filter by a specific date span, shown as explicit start and end dates. Default is [!UICONTROL Last 30 days].
-->