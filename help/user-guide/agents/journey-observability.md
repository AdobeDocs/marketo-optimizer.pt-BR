---
title: Monitorar e depurar a progressão da Jornada
description: Saiba como usar a habilidade de Observabilidade da Jornada no bate-papo do Colaborador para depurar e monitorar como as pessoas e os leads se movem pelas jornadas, decisões de caminho dividido e tempo.
source-git-commit: 9db94582512d95f6c07d4e978a0a27291b471900
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 0%

---

# Monitorar e depurar a progressão da jornada

A habilidade [_Observability_ da Jornada](./skills.md#journeys) em [!DNL Adobe Marketo Optimizer] responde a perguntas de linguagem natural sobre como as pessoas e os clientes em potencial se movem pelas jornadas. Use-o na [Interface de chat do Colaborador](./chat-interface.md) para rastrear a progressão, entender decisões de caminho dividido, analisar pessoas em nós de jornada e verificar métricas de tempo. Você também pode perguntar sobre padrões de comportamento nas jornadas.

* **Habilidade** - `journey-observability`
* **Invocação** - Faça uma pergunta em linguagem natural ou use um comando de barra para executar a habilidade de Observabilidade do Jornada. Por exemplo: _&quot;Como o demo_ lead_24@company.com passou pela LeadNurtureJourney?&quot;_
* **Lê de** - [!DNL Marketo Optimizer] dados de jornada; lê [!DNL Marketo Engage] listas estáticas para verificar associação à lista

## Exibir detalhes da pessoa ou do cliente potencial {#person-details}

Solicite detalhes básicos e somente leitura sobre uma pessoa ou cliente potencial para estabelecer o contexto antes de investigar sua jornada. Forneça o endereço de email, a ID do cliente potencial ou o nome do cliente potencial da pessoa.

* _&quot;Forneça-me informações básicas sobre o lead demo_ lead_24@company.com.&quot;_
* _&quot;Qual é o cargo e o país do perfil john.doe@company.com?&quot;_
* _&quot;Mostrar o email e a função do lead_ 01.&quot;_

## Rastrear a progressão em uma jornada {#journey-progression}

Pergunte como uma pessoa ou lead se moveu por uma jornada para ver a entrada, a saída, a duração e o caminho que tomou. Forneça o endereço de email ou a ID do cliente potencial da pessoa e o nome da jornada.

* _&quot;Como o demo_ lead_24@company.com passou pela LeadNurtureJourney?&quot;_
* _&quot;Por quais nós o john.doe@company.com passou na jornada de Demonstração do Produto?&quot;_

## Compreender as decisões de divisão de caminhos {#split-path-analysis}

Pergunte por que uma pessoa ou cliente potencial tomou ou não tomou um caminho específico em um nó dividido. A Observability Jornada explica a decisão usando os valores de atributo avaliados nesse momento. Forneça o endereço de email da pessoa ou a ID do cliente potencial, o nome da jornada e a ID do nó dividido.

* _&quot;Por que demo_ lead_24@company.com foi para o caminho &#39;Altamente engajado&#39; no nó dividido c764a9?&quot;_
* _&quot;Por que john.doe@company.com não tomou o caminho qualificado no nó ab123f em LeadNurtureJourney?&quot;_
* _&quot;Compare por que lead_ 01 e lead_02 tomaram caminhos diferentes no nó dividido x99f3b.&quot;_

## Analisar pessoas em nós do jornada {#node-analysis}

Solicitar contagens de pessoas ou clientes potenciais e detalhes em um nó de jornada ou caminho dividido. Filtrar resultados por nível de persona, função, local ou envolvimento. Forneça a ID do nó.

* _&quot;Dê-me todas as pessoas que estão atualmente no caminho &#39;Alto engajamento&#39; do nó-459c7c.&quot;_
* _&quot;Quantos clientes potenciais estão no nó de qualificação da jornada Demo Nurture?&quot;_
* _&quot;Mostrar clientes em potencial no caminho de divisão de &#39;Baixa intenção&#39; filtrado por função: Gerente de Marketing.&quot;_

## Identificar padrões em jornadas {#pattern-recognition}

Peça à Observabilidade da Jornada para identificar caminhos comuns, pontos de interrupção e comportamentos repetidos em uma jornada. Forneça o nome da jornada e, opcionalmente, um período, persona, produto ou conta para limitar os resultados.

* _&quot;Quais são os caminhos mais comuns que os SDRs tomam na jornada de demonstração do produto?&quot;_
* _&quot;Onde os clientes em potencial geralmente aparecem na LeadNurtureJourney?&quot;_
* _&quot;Há atrasos incomuns ou caminhos inesperados na jornada do Q1 Nurture?&quot;_

## Verificar métricas operacionais e de tempo {#operational-metrics}

Pergunte sobre tempos de entrada, durações de espera, latência de transição e progressão paralisada para uma jornada. Forneça o nome da jornada e, opcionalmente, uma ID de nó ou um identificador de pessoa.

* _&quot;Quando o john.doe@company.com entrou na jornada de Acompanhamento de Demonstração?&quot;_
* _&quot;Por quanto tempo os clientes potenciais normalmente aguardam no nó de qualificação em LeadNurtureJourney?&quot;_
* _&quot;Quais clientes em potencial foram paralisados na jornada de Acompanhamento de Demonstração por mais de sete dias?&quot;_

## Limitações {#limitations}

| Limitação | Detalhe |
|---|---|
| Editar atributos de pessoa ou lead | Não suportado. Atualizar registros de pessoa e cliente potencial diretamente em [!DNL Marketo Engage] ou [!DNL Marketo Optimizer]. |
| Criação, edição, pausa ou retomada de jornadas | Não suportado. Em vez disso, use a [tela de jornada](../marketing/person-journeys.md) ou uma habilidade de edição de jornada em [habilidades de colega](./skills.md#journeys). |
| Alteração da lógica de divisão ou da configuração de jornada | Não suportado. Edite os caminhos divididos diretamente na [tela de jornada](../marketing/split-merge-paths-nodes.md). |
| Composição de grupo de compras ou rollups de nível de conta | Fora do escopo. Jornada relatórios de Observabilidade somente no nível da pessoa e do lead. |
| Alteração de agendamentos ou tempo de jornada | Não suportado. |
