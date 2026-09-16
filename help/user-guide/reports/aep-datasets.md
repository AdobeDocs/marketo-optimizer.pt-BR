---
title: Conjuntos de dados do Experience Platform
description: Saiba mais sobre os conjuntos de dados que o Marketo Otimizer grava no Adobe Experience Platform para potencializar a geração de relatórios e a consulta ad hoc do Customer Journey Analytics.
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
source-git-commit: 1ebb0036699252c50f33ba6c0f4a56e8e670aacd
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 4%
---

# Conjuntos de dados do Experience Platform

[!DNL Adobe Marketo Optimizer] replica dados de cliente potencial, jornada e atividade em [!DNL Adobe Experience Platform] conjuntos de dados. Esses conjuntos de dados alimentam a página [!UICONTROL Relatórios] e a experiência de relatório [!DNL Adobe Customer Journey Analytics] incorporada. Você também pode consultá-los diretamente com [!DNL Query Service] para Ad Hoc Analysis.

Os conjuntos de dados são gerenciados pelo sistema. Uma conexão em [!DNL Customer Journey Analytics] os vincula à exibição de dados usada pelos relatórios do [!DNL Marketo Optimizer], portanto, você mesmo não precisa criar essa conexão. Esta conexão é a mesma que você estabelece ao selecionar **[!UICONTROL Analisar no CJA]** em uma seção de relatório. Consulte [Analisar um relatório no Customer Journey Analytics](./reports-overview.md#analyze-a-report-in-cja).

## Conjuntos de dados disponíveis {#available-datasets}

Os conjuntos de dados a seguir são preenchidos para cada instância [!DNL Marketo Optimizer].

>[!NOTE]
>
>Cada nome de conjunto de dados usa o prefixo `AJOB2B`, que indica o nome do sistema para os dados [!DNL Marketo Optimizer]. Esse comportamento é esperado, e você pode usar esses nomes para localizar os conjuntos de dados em sua sandbox [!DNL Experience Platform].

| Conjunto de dados | Esquema | Descrição |
| --- | --- | --- |
| `AJOB2B - Person` | Pessoa | Atributos de lead padrão. |
| `AJOB2B - PersonActivity` | Atividade de pessoa | Eventos de atividade associados a uma pessoa. |
| `AJOB2B - PersonActivityType` | Tipo de atividade da pessoa | Tipos de atividade associados a uma pessoa. |
| `AJOB2B - PersonActivityTypeEngagementMapping` | Tipo de atividade de pessoa Mapeamento de envolvimento | Mapeia tipos de atividades para sua classificação de engajamento, evento de canal e direcionalidade. |
| `AJOB2B - Journey` | Jornada | Lista de jornadas e seus metadados de ciclo de vida. |
| `AJOB2B - JourneyNode` | Jornada nó | Lista de nós em uma jornada e seus metadados associados. |
| `AJOB2B - EngagementAsset` | Ativo de participação | Pesquisa unificada de IDs de ativos de envolvimento e nomes de exibição em todos os tipos de ativos de envolvimento. |

## Consultar conjuntos de dados com o Serviço de consulta {#query-service}

Use [!DNL Query Service] para executar consultas SQL ad hoc nesses conjuntos de dados quando precisar de análise fora dos relatórios [!DNL Customer Journey Analytics]. O acesso à consulta requer as [!DNL Experience Platform] permissões apropriadas para sua sandbox. Para obter a sintaxe e a configuração da consulta geral, consulte [Serviço de consulta](https://experienceleague.adobe.com/pt-br/docs/experience-platform/query/home){target="_blank"}.

![Editor do Serviço de Consulta mostrando uma consulta SELECT sobre o conjunto de dados ajob2b_jornada e uma tabela de registros de jornada resultantes.](./assets/aep-query-service.png){width="800" zoomable="yes"}

>[!NOTE]
>
>Esses conjuntos de dados são somente leitura. Para alterar quais dados [!DNL Marketo Optimizer] captura, atualize os dados de origem em [!DNL Marketo Optimizer] ou [!DNL Marketo Engage] em vez de editar um conjunto de dados diretamente.
