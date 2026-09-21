---
title: Gerar relatórios do Analytics
description: Saiba como usar a habilidade do Surface Analytics no bate-papo com colegas de trabalho para gerar relatórios de atividade, email, cliente potencial, segmento e jornada a partir de prompts em linguagem natural.
autotag-review: '2026-09-21T14:58:26.479Z'
TQID: 'https://experienceleague.adobe.com/BSDEihjdpz-YZjMWrYTmIuyjqtcjRHRrJdz4xPFZbHU'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
    internal-label: Chat Interface
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
subfeature_v2:
  - id: b9e5c7f3-be30-563c-9e41-cc8ea76e2fee
    internal-label: Skills
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 1dcc3bcdc59114c7fc1e16178db8921ae173b955
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%
---
# Gerar relatórios de análise

A habilidade [_Surface Analytics_](./skills.md#analytics-reporting) em [!DNL Adobe Marketo Optimizer] responde a perguntas de linguagem natural sobre seus dados. Use-o na [Interface de chat do parceiro](./chat-interface.md) para explorar tendências de atividades, desempenho de email, dados de clientes potenciais e de contas, associação de segmentos e listas e métricas de jornada. Os resultados retornam como gráficos e tabelas, de modo que não é necessário criar uma consulta ou painel manualmente.

* **Habilidade** - `surface-analytics`
* **Invocação** - Faça uma pergunta em linguagem natural ou use um comando de barra para executar a habilidade do Surface Analytics. Por exemplo: _&quot;Mostrar as contagens de atividades diárias dos últimos 30 dias.&quot;_
* **Lê de** - [!DNL Marketo Optimizer] dados de análise; lê [!DNL Marketo Engage] dados de análise para perguntas que abrangem ambos os produtos

>[!NOTE]
>
>Os dados do relatório são atualizados a cada duas horas. Os resultados podem não refletir a atividade das últimas duas horas.

## Exibir tendências de atividades {#activity-trends}

Pergunte sobre contagens de atividades diárias ou semanais e separe os resultados por tipo de atividade ou área do produto.

* _&quot;Mostrar as contagens de atividades diárias dos últimos 30 dias.&quot;_
* _&quot;Quais são os principais tipos de atividades esta semana?&quot;_
* _&quot;Analisar a atividade do mês passado por área de aplicativo.&quot;_

## Verificar desempenho do email {#email-performance}

Pergunte sobre o volume de envio, as taxas de abertura e de clique, as rejeições e os cancelamentos de assinatura de seus programas de email.

* _&quot;Qual é a taxa de abertura de email por jornada?&quot;_
* _&quot;Mostre-me as taxas de cliques dos últimos 90 dias.&quot;_
* _&quot;Quantas cancelamentos de inscrição recebemos na semana passada?&quot;_

## Analisar dados de cliente potencial e de conta {#lead-account-data}

Pergunte sobre a distribuição de pontuação de leads, detalhamentos de persona e rollups geográficos ou firmográficos.

* _&quot;Mostrar a distribuição de pontuação entre clientes potenciais.&quot;_
* _&quot;Quantas pessoas estão em cada conta?&quot;_
* _&quot;Analisar clientes em potencial por persona.&quot;_

## Revisar segmento e listar associação {#segment-list-membership}

Pergunte quem pertence a uma lista ou segmento específico.

* _&quot;Quantas pessoas estão na lista de Preparação T1?&quot;_
* _&quot;Qual segmento tem mais membros?&quot;_

## Explorar métricas do jornada {#journey-metrics}

Pergunte sobre associação à jornada, taxas de conclusão, passagem de nó e análise da funnel.

* _&quot;Qual é a taxa de conclusão da jornada de acompanhamento da demonstração?&quot;_
* _&quot;Quantas pessoas estão em cada nó da LeadNurtureJourney?&quot;_

## Faça perguntas entre produtos {#cross-product}

O Surface Analytics pode responder perguntas que abrangem dados de [!DNL Marketo Engage] e [!DNL Marketo Optimizer] em um único prompt.

* _&quot;Qual é meu email de melhor desempenho no LumaSecure e no LumaStorage?&quot;_

## Limitações {#limitations}

| Limitação | Detalhe |
|---|---|
| Editar ou criar registros | Não suportado. O Surface Analytics só lê e relata os dados existentes. |
| Nomes legíveis nos resultados | Nem sempre está disponível. Alguns relatórios mostram uma ID interna, como uma jornada ou ID de email, em vez de um nome. |
| Cartões de relatório duplicados | Ocasionalmente, uma única pergunta pode retornar mais de um cartão de relatório para o mesmo resultado. |
