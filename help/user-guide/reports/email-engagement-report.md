---
title: Relatório de engajamento no email
description: Saiba mais sobre o relatório Envolvimento de email no Adobe Marketo Otimizer, que mostra as métricas de capacidade de entrega e engajamento de email por email e jornada.
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
source-git-commit: 6e919a66af259ea1f5facf7f5c3e811d76101e85
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 0%
---

# Relatório de engajamento com o email

<!-- SPHR-32511: Filter by Program, Filter by Audience, and the program data point for the email performance table are not documented here pending delivery. -->

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

## Filtros {#filters}

Use filtros para restringir o relatório a uma jornada ou persona específica. Selecione **[!UICONTROL Redefinir tudo]** para limpar todos os filtros e retornar ao modo de exibição padrão.

* **[!UICONTROL Nome da Jornada (Evento)]** - Filtre pela jornada que enviou o email. O padrão é [!UICONTROL Nenhum filtro].
* **[!UICONTROL Persona (Evento)]** - Filtre pela pessoa associada ao email. O padrão é [!UICONTROL Nenhum filtro].