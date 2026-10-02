---
title: Arquitetura de dados
description: Saiba como a Marketo Optimizer e a Marketo Engage compartilham dados, incluindo direção e latência de sincronização de entidade, fluxo de dados de atividade e isolamento de dados baseado em sandbox.
role: User, Admin
autotag-review: '2026-10-01T18:40:38.362Z'
TQID: 'https://experienceleague.adobe.com/oelEtys81g6TzM8bi-qy1nuWw6scOBry7tbZkMkZ6u0'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
  - id: 3cf5f37e-e87e-5179-812b-53ce05d7eebb
    internal-label: Setup
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
    internal-label: Audiences
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
  - id: d4203578-d294-5145-b397-f26f4488a904
    internal-label: Channels
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
source-git-commit: 518a807aeed2471772b4f0a4d6d8d525cd3e22fd
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 1%
---

# Arquitetura de dados

[!DNL Adobe Marketo Optimizer] integra-se com [!DNL Adobe Marketo Engage] para fornecer uma visão abrangente dos clientes em potencial B2B. Uma sincronização bidirecional e confiável mantém os dois produtos alinhados, de modo que eles compartilhem uma visão de pessoas, empresas, objetos personalizados e atividades. [!DNL Marketo Engage] permanece a fonte autoritativa para dados de pessoas. Cada instância [!DNL Marketo Optimizer] está emparelhada a uma instância [!DNL Marketo Engage].

## Base de dados {#data-foundation}

[!DNL Marketo Optimizer] e [!DNL Marketo Engage] compartilham uma base de dados comum que os mantém sincronizados enquanto alimentam análises downstream.

![Diagrama de arquitetura do Marketo Optimizer e do Marketo Engage que mostra como os serviços, tempos de execução e armazenamentos de dados dos dois produtos se conectam entre o Microsoft Azure e o AWS](./assets/marketo-optimizer-architecture.svg)

Em um alto nível:

* **[!DNL Marketo Engage]** é a fonte definitiva para dados de cliente potencial e objeto personalizado, o que garante a integridade dos dados no ponto de captura.
* Uma **camada do Data Broker** coordena como os dados se movem entre os dois produtos. Ele agrega dados compartilhados e replicados em um banco de dados operacional pronto para uso. Todo o Exchange é executado em um único cluster Aurora MySQL.
* **[!DNL Marketo Optimizer]** é a fonte autoritativa para as atividades de jornada executadas.

## Sincronização de entidade {#entity-sync}

Cada tipo de entidade sincroniza na direção e na velocidade que melhor protege a integridade dos dados.

| Entidade [!DNL Marketo Engage] | Direção da sincronização | Latência |
| --- | --- | --- |
| Lead | Bidirecional | Menos de 1 segundo |
| Empresa | Bidirecional | Menos de 1 segundo |
| Objeto personalizado | Unidirecional | Menos de 5 segundos |
| Atividade | Unidirecional | Menos de 5 segundos |
| associação ao programa | Não sincronizado | Não aplicável |
| Ativos | Não sincronizado | Não aplicável |

A sincronização funciona de duas maneiras:

* **Clientes potenciais, empresas e objetos padrão:** [!DNL Marketo Engage] possui a tabela de pessoas e a compartilha por meio de exibições de banco de dados de leitura e gravação. As atualizações em um produto aparecem no outro imediatamente, e nenhuma cópia duplicada é criada.
* **Objetos personalizados:** Os dados são replicados de [!DNL Marketo Engage] em segundos. Atualizações de esquema em [!DNL Marketo Engage] estão imediatamente disponíveis para jornadas ativas.

[!DNL Marketo Engage] e [!DNL Marketo Optimizer] não sincronizam a associação ou os ativos do programa. Essa exclusão preserva a velocidade e a integridade do sistema.

>[!NOTE]
>
>Os dados sincronizados com [!DNL Marketo Optimizer] e com o data warehouse acabam sendo consistentes. O tempo depende da captura de dados de alteração subjacente, do lote ou do mecanismo de fluxo.

Esse design quase em tempo real fornece dados atuais em jornadas e relatórios. Você pode acompanhar rapidamente em leads de alta prioridade. Você também pode usar dados de contexto B2B, como uso e intenção do produto, nas decisões de jornada conforme eles são alterados.

## Fluxo de dados da atividade {#activity-flow}

As atividades seguem um caminho separado das outras entidades. Cada atividade passa por cinco estágios:

1. **Captura primária:** [!DNL Marketo Engage] grava a atividade em seu banco de dados compartilhado e a indexa no Apache SOLR para pesquisa rápida em [!DNL Marketo Engage].
1. **Reconhecimento entre produtos:** [!DNL Marketo Engage] publica a atividade no pipeline de atividade, portanto, [!DNL Marketo Optimizer] a recebe imediatamente.
1. **Transformação analítica:** o tempo de execução do jornada processa a atividade e a grava na Snowflake, que transforma os dados operacionais em dados prontos para análise. Todos os estágios até o momento são executados no Amazon Web Services (AWS).
1. **Destino downstream:** [!DNL Marketo Optimizer] replica a atividade em [!DNL Adobe Experience Platform] conjuntos de dados.
1. **Relatórios:** o feed dos conjuntos de dados inseriu [!DNL Adobe Customer Journey Analytics] relatórios. [!DNL Customer Journey Analytics] pode ser hospedado no Microsoft Azure ou AWS. Você também pode consultar os conjuntos de dados com [!DNL Query Service]. Consulte [conjuntos de dados do Experience Platform](./reports/aep-datasets.md).

Os públicos-alvo de jornadas e eventos podem usar [!DNL Marketo Optimizer] atividades e um subconjunto de [!DNL Marketo Engage] atividades. Você usa ambos os conjuntos da mesma maneira. [!DNL Marketo Optimizer] atividades não são enviadas de volta para [!DNL Marketo Engage].

Use atividades como preenchimentos de formulário, visitas da Web e envolvimento de email para acionar, filtrar e ramificar jornadas de pessoas:

* [Acionadores de evento para o nó Escutar um evento](./marketing/listen-for-event-nodes.md#event-triggers)
* [Filtros de evento para o nó Escutar um evento](./marketing/listen-for-event-nodes.md#event-filters)
* [Filtros de pessoa correspondentes para nós de caminhos divididos](./marketing/split-merge-paths-nodes.md#matched-person-filters)
* [Públicos-alvo baseados em eventos](./audiences/event-based-audiences.md)

## Isolamento de dados e sandboxes {#data-isolation}

[!DNL Marketo Engage], [!DNL Marketo Optimizer] e [!DNL Experience Platform] compartilham dados de clientes como parte dessa arquitetura. A Adobe isola logicamente seus dados de outros locatários usando [!DNL Experience Platform] sandboxes. Os dados são movidos por canais seguros e criptografados. A Adobe o armazena no Adobe Managed Services com controles de acesso e criptografia padrão do setor.

Cada instância do [!DNL Marketo Optimizer] tem um cartão de produto dedicado no [!DNL Adobe Admin Console] e uma sandbox dedicada. O Adobe provisiona ambos automaticamente, de modo que você não crie uma sandbox. O nome da sandbox usa o padrão `mktoaep<prefix>`, em que o prefixo é seu prefixo [!DNL Marketo Engage]. Se você usar o [!DNL Marketo Optimizer] com mais de uma instância do [!DNL Marketo Engage], cada instância terá seu próprio cartão de produto e sandbox.

[!DNL Marketo Optimizer] está disponível somente nesta sandbox, mesmo se sua organização tiver outras sandboxes.

O provisionamento não atribui acesso à sandbox. As funções normalmente têm acesso à sandbox `prod` padrão, mas [!DNL Marketo Optimizer] não a usa. Atribua explicitamente a sandbox dedicada a cada função do [!DNL Experience Platform], ou os usuários não poderão trabalhar no [!DNL Marketo Optimizer]. Use grupos de usuários para adicionar e remover usuários sem repetir a configuração de função. Para obter o procedimento completo, consulte [Acesso e permissões do usuário](./start/user-management.md).

[!DNL Marketo Optimizer] também usa serviços [!DNL Experience Platform] em segundo plano. Isso inclui o registro do esquema, destinos para exportação de mídia paga, controle de acesso e [!DNL Customer Journey Analytics]. Você não configura esquemas ou namespaces. [!DNL Marketo Optimizer] não requer [!DNL Real-Time Customer Data Platform], Perfil de cliente em tempo real ou segmentação.

>[!WARNING]
>
>Não exclua a sandbox [!DNL Marketo Optimizer] dedicada. A exclusão é permanente e não pode ser desfeita. Reprovisionar [!DNL Marketo Optimizer] para recuperar.
