---
title: Interoperabilidade com o Marketo Engage
description: Saiba o que a Marketo Optimizer compartilha com o Marketo Engage, incluindo dados, atividades e públicos-alvo, e como enviar email de qualquer produto em suas jornadas.
role: User, Admin
autotag-review: '2026-10-01T18:40:01.444Z'
TQID: 'https://experienceleague.adobe.com/7TB6JG9yiUT-l0VevNW4tvwieCyFjOypZwI0SlUzmmY'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
    internal-label: Audiences
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
  - id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
    internal-label: Programs
  - id: d4203578-d294-5145-b397-f26f4488a904
    internal-label: Channels
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 518a807aeed2471772b4f0a4d6d8d525cd3e22fd
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 0%
---

# Interoperabilidade com o Marketo Engage

[!DNL Adobe Marketo Optimizer] e [!DNL Adobe Marketo Engage] compartilham dados, algumas atividades e públicos. Eles mantêm os ativos separados. Entenda o que cada produto compartilha para decidir onde criar e enviar seu marketing.

## Compartilhado entre os produtos {#shared}

* [!DNL Marketo Engage] clientes em potencial e atividades fluem para [!DNL Marketo Optimizer] automaticamente.
* O Jornada pode escutar atividades de [!DNL Marketo Engage].
* Públicos-alvo baseados em eventos podem incluir pessoas que realizam [!DNL Marketo Engage] atividades.
* As ações de jornada podem interagir com [!DNL Marketo Engage]. Você pode adicionar ou remover pessoas de uma lista [!DNL Marketo Engage] e solicitar uma campanha [!DNL Marketo Engage].
* [!UICONTROL Scoring Studio] classifica as pessoas em relação às atividades [!DNL Marketo Engage] e [!DNL Marketo Optimizer]. Você pode usar as pontuações em [!DNL Marketo Engage].
* Ambos os produtos compartilham endereços IP e subdomínios.
* Os relatórios conversacionais unificados abrangem ambos os produtos.

## Mantido separado {#separate}

* **Assets:** emails, modelos, programas e imagens vivem em repositórios separados.
* **Atividades:** [!DNL Marketo Optimizer] atividades não são compartilhadas de volta em [!DNL Marketo Engage].
* **Campos e limites:** os campos personalizados derivados de [!DNL Marketo Optimizer] não estão disponíveis em [!DNL Marketo Engage]. Os limites de comunicação são definidos separadamente em cada produto.

Para obter detalhes sobre a sincronização, consulte [Sincronização de entidade](./data-architecture.md#entity-sync).

## Enviar email do Marketo Engage {#send-from-marketo}

Use esta abordagem para executar jornadas, etapas de espera e decisões de IA no [!DNL Marketo Optimizer] enquanto o [!DNL Marketo Engage] envia cada email.

1. Em [!DNL Marketo Optimizer], crie uma jornada que inclua etapas de espera e decisões de IA.
1. Para cada etapa de envio, adicione a ação **[!UICONTROL Solicitar campanha do Marketo Engage]** e selecione uma campanha [!DNL Marketo Engage] correspondente.
1. Opcional: adicione um programa padrão abrangente em [!DNL Marketo Engage] para agregar relatórios de sucesso na jornada.

Para obter detalhes da ação, consulte [Executar um nó de ação](./marketing/action-nodes.md).

[!DNL Marketo Engage] envia o email através das configurações de canal existentes. Como [!DNL Marketo Engage] envia o email, você não configura canais ou emails em [!DNL Marketo Optimizer]. Além disso:

* Envios, aberturas e cliques são registrados em [!DNL Marketo Engage].
* O gerenciamento de cancelamento de inscrição e a governança de email se aplicam em [!DNL Marketo Engage].
* A atividade de email alimenta suas campanhas de pontuação existentes do [!DNL Marketo Engage].
* As campanhas de sincronização do Salesforce acionadas pela atividade são executadas conforme esperado.
* Cada envio mapeia para uma campanha [!DNL Marketo Engage], para que você acompanhe a associação ao programa por campanha de email e relate em programas familiares.

## Enviar email do Marketo Optimizer {#send-from-optimizer}

Use esta abordagem para criar a jornada e enviar o email inteiramente em [!DNL Marketo Optimizer]. O [!DNL Marketo Engage] permanece o sistema de registro da entrega para o seu sistema de CRM (relacionamento com o cliente).

1. Configure o canal de email. Crie modelos de email e configure o endereço IP e o subdomínio, os links de cancelamento de inscrição e as páginas de aterrissagem. Consulte [Entregabilidade de email](./start/email-deliverability.md).
1. Definir limites de comunicação em [!DNL Marketo Optimizer]. Os limites de comunicação compartilhada não estão disponíveis.
1. Crie a jornada com públicos-alvo, decisões de IA e o próximo melhor caminho.
1. Enviar email de [!DNL Marketo Optimizer]. [!DNL Marketo Optimizer] registra as atividades.
1. Marque pessoas no [!UICONTROL Scoring Studio] para criar um modelo entre as atividades [!DNL Marketo Engage] e [!DNL Marketo Optimizer]. Consulte [Scoring Studio](./labs/scoring-studio.md).

Cancelamentos de assinatura para sincronizar com [!DNL Marketo Engage] automaticamente por meio de campos compartilhados. A atividade de email [!DNL Marketo Optimizer] não é enviada de volta para [!DNL Marketo Engage], mas o [!UICONTROL Scoring Studio] ainda a usa.

### Entregar leads para vendas {#hand-off}

[!DNL Marketo Optimizer] não tem integração direta com o CRM. A rota inicia em [!DNL Marketo Engage] com um destes métodos:

* **Baseado em pontuação:** o campo de pontuação aparece em [!DNL Marketo Engage], e uma campanha inteligente sincroniza o lead para seu CRM.
* **Baseado em atividade:** uma jornada [!DNL Marketo Optimizer] escuta a atividade e adiciona o cliente potencial a uma campanha inteligente [!DNL Marketo Engage].
* **Associação de programa**: a jornada fica em um programa [!DNL Marketo Optimizer], portanto, você pode acompanhar o status do início ao fim.
