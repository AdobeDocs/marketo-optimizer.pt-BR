---
title: Relatórios
description: Entenda a guia Relatórios no Adobe Marketo Otimizer, incluindo suas seções de relatório, opções de exportação e agendamento e como alterar o intervalo de datas.
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
source-git-commit: 32017a2577b7f31632080215ba91b9454c51b9ef
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 2%
---

# Relatórios

A guia [!UICONTROL Relatórios] fornece insights de desempenho sobre o [!DNL Adobe Marketo Optimizer], incluindo envolvimento da jornada, desempenho de email e atividade da Web. Na navegação à esquerda, selecione **[!UICONTROL Relatórios]** para abri-lo.

Cada relatório é compilado em [!DNL Adobe Customer Journey Analytics] e incorporado diretamente em [!DNL Marketo Optimizer]. Clique no ícone _Lista_ ( ![Ícone Lista](../assets/do-not-localize/icon-table-of-contents.svg) ) para usar o painel **[!UICONTROL Índice]** à esquerda para saltar entre as seções.

![Página de relatórios listando as seções Visão geral da Jornada de pessoas, Envolvimento, Envolvimento de email e Envolvimento com a Web](./assets/reports-table-of-contents.png){width="800" zoomable="yes"}

## Seções do relatório {#report-sections}

A guia [!UICONTROL Relatórios] organiza relatórios pré-criados em quatro seções. Cada seção tem um ou mais itens baixáveis e sua própria página de documentação com detalhes sobre suas métricas e visualizações.

| Seção | Itens baixáveis | Página do relatório |
| --- | --- | --- |
| [!UICONTROL Visão geral da Jornada de pessoa] | Número de jornadas ativas | [Relatório de visão geral da Jornada da pessoa](./person-journey-overview-report.md) |
| [!UICONTROL Engajamento] | Engajamento por pessoas, Engajamento pessoal ao longo do tempo | [Relatório de engajamento](./engagement-report.md) |
| [!UICONTROL Engajamento no email] | Engajamento no email | [Relatório de engajamento no email](./email-engagement-report.md) |
| [!UICONTROL Participação na Web] | Principais visualizações da página | [Relatório de participação na Web](./web-engagement-report.md) |

## Relatórios de registro individual {#individual-record-reports}

Alguns relatórios se concentram em um único registro, em vez de uma visualização em toda a seção, e são acessados de uma área diferente no aplicativo.

* Para obter o desempenho da otimização de tempo de envio de email, abra o relatório na interface de chat do [!UICONTROL Colaborador]. Para ver as etapas, consulte [Otimização do tempo de envio de email](../marketing/email-send-time-optimization.md#reporting).
* Para o progresso de uma pessoa em uma única jornada, abra o relatório nessa jornada.

## Exportar um relatório {#export-a-report}

Selecione **[!UICONTROL Compartilhar]** na parte superior da página do relatório para exportar ou agendar a entrega de seus dados.

![Compartilhar menu com as opções Baixar CSV, Baixar PDF, Agendar exportação e Gerenciar agendamentos](./assets/reports-share-menu.png){width="500"}

* **[!UICONTROL Baixar CSV]** - Exporte os dados do relatório como valores de texto sem formatação.

* **[!UICONTROL Baixar PDF]** - Exporte todas as tabelas e visualizações visíveis no relatório como um arquivo PDF.

* **[!UICONTROL Exportação agendada]** - Configure uma exportação recorrente do relatório, entregue semanal ou mensalmente como um arquivo CSV ou PDF.

* **[!UICONTROL Gerenciar agendas]** - Revise e gerencie exportações agendadas existentes. A opção mostra uma contagem em execução, como `3/10`, de agendamentos usados em relação ao limite da organização.

>[!NOTE]
>
>Sua organização pode ter no máximo 10 exportações programadas em todos os relatórios, em uma frequência semanal ou mensal. Se você não for um administrador, poderá gerenciar apenas suas próprias exportações programadas. Os administradores podem visualizar e gerenciar cada exportação agendada na organização.

## Analisar um relatório em [!DNL Customer Journey Analytics] {#analyze-a-report-in-cja}

>[!AVAILABILITY]
>
>Esta função estará disponível se sua organização tiver uma licença para [!DNL Adobe Customer Journey Analytics] e você tiver atribuído o perfil de produto a ela.

Selecione **[!UICONTROL Analisar no CJA]** em qualquer seção de relatório para abri-la no Workspace [!DNL Adobe Customer Journey Analytics], onde é possível criar visualizações personalizadas além das disponíveis no relatório inserido.

## Alterar intervalo de datas {#change-the-date-range}

Cada seção de relatório mostra dados para um intervalo de datas específico, exibidos no canto superior direito da seção. Clique nos campos de intervalo de datas para exibir as ferramentas de seleção de data e selecione o intervalo de datas. É possível escolher uma predefinição diferente ou definir um intervalo personalizado.

![Seletor de intervalo de datas com um calendário de dois meses, campos de datas inicial e final e opções predefinidas](./assets/reports-date-range.png){width="600"}
