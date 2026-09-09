---
title: Configurar e analisar intenção
description: Saiba como configurar os pesos da atividade para o modelo de pontuação de intenção e analisar a intenção no nível de lead com relatórios de classificação, perfil, tendência e comparação.
source-git-commit: 8b3ea5f52fc50ea6c995ace44dece90247deff8b
workflow-type: tm+mt
source-wordcount: '978'
ht-degree: 0%

---


# Configurar e analisar a intenção

Em [!DNL Adobe Marketo Optimizer], o Colaborador fornece duas habilidades na categoria _Intenção_. Cada cliente pesa as atividades de marketing de forma diferente, portanto, essas habilidades permitem que você configure o que é importante para sua empresa. Você pode validar o que o pipeline de intenção produziu.

| Habilidade | Comando | O que faz |
| --- | --- | --- |
| **Configuração de intenção** | `/intent-configuration` (alias `/intent-config`) | Configurar pesos da atividade para o modelo de pontuação de intenção da pessoa |
| **Analisar intenção** | `/analyze-intent` | Consultar e validar relatórios de classificação de intenção, tendência, taxonomia de produto e palavra-chave no nível do cliente potencial e de comparação |

Selecionar uma habilidade insere sua descrição como um prompt inicial na entrada do chat, que pode ser editado antes do envio.

## Configurar o modelo de ponderação {#configure-model}

Para configurar os pesos da atividade para o modelo de pontuação de intenção, siga estas etapas gerais. Para obter mais informações sobre configuração e ponderação de pontuação, consulte [_Configuração de Intenção_](../audiences/intent-configuration.md).

1. Chame a habilidade (`/intent-configuration`) e pressione **Enter**.

   O colaborador abre o painel **[!UICONTROL Configuração de intenção]** como uma guia do espaço de trabalho. O painel lista cada atividade de intenção do pipeline, mostrando uma pontuação de **[!UICONTROL IA sugerida]** e uma pontuação **[!UICONTROL Ponderação]** editável para cada uma. Ela também lista os modelos que já existem para seu locatário. Somente um modelo pode estar _[!UICONTROL Ativo]_ a qualquer momento: aquele que está liderando a pontuação no momento.

1. Para fazer alterações, abra um modelo _[!UICONTROL Rascunho]_ existente ou selecione **[!UICONTROL Duplicar]** no modelo _[!UICONTROL Ativo]_ para começar com seus pesos atuais.

1. Ajustar pesos linha por linha.

   Por exemplo, marque uma atividade de baixo valor como **[!UICONTROL Adicionar à oportunidade]** como **[!UICONTROL Trivial]** e gere um **[!UICONTROL Clique em Email]** ou **[!UICONTROL Clique em Link]** para **[!UICONTROL Importante]** se essas atividades forem mais importantes para a sua empresa.

1. Selecione **[!UICONTROL Salvar]**.

   Salvar solicita que você ative o modelo agora. A confirmação substitui o modelo _[!UICONTROL Ativo]_ atual, que é rebaixado automaticamente.

## Pontuação de intenção

A pontuação de intenção de um lead considera três aspectos:

* **O peso configurado aqui** para cada tipo de atividade.
* **Relevância de conteúdo**: palavras-chave extraídas dos ativos vinculados a cada atividade.
* **Frequência**: quantas vezes o lead interagiu com esse conteúdo.

Para obter detalhes sobre essas métricas, incluindo o peso sugerido pela IA, relevância do conteúdo e limitações, consulte [Configuração de intenção](../audiences/intent-configuration.md).

## Relatórios de intenção

Para introduzir os quatro tipos de relatório que ele pode gerar, chame `/analyze-intent` para solicitar o Coworker. O colaborador aguarda uma solicitação de acompanhamento que nomeia um cliente potencial, produto ou comparação. Cada relatório é aberto como sua própria guia no painel do espaço de trabalho, e o Colaborador também adiciona um cartão de resumo no chat com um botão _[!UICONTROL Abrir relatório]_.

### Relatório de classificação de intenção

**Prompt sugerido:** _&quot;Mostrar meus principais clientes em potencial de alta intenção para o &lt;product>&quot;_

Classifica os clientes em potencial por intensidade de sinal de intenção para um produto ou palavra-chave. As colunas incluem lead, email, conta, setor, produtos, pontuação, nível de intenção e origem da atividade principal. A coluna delta _[!UICONTROL 7 dias]_ mostra como a pontuação de intenção foi movida na última semana. A coluna _[!UICONTROL Última atualização]_ mostra quando o lead interagiu pela última vez, ou seja, quando a pontuação foi alterada pela última vez. Os filtros para nível de produto e intenção são menus suspensos em tempo real, para que você não fique limitado ao que digitou no prompt. As colunas são classificáveis.

Outros prompts que abrem o mesmo relatório:

* &quot;Classifique os 10 principais clientes em potencial por pontuação de intenção para o Photoshop&quot;
* &quot;Listar clientes em potencial com alta intenção para o Photoshop&quot;
* &quot;Mostre-me clientes potenciais cuja pontuação de intenção para o Photoshop foi a que mais saltou esta semana&quot;
* &quot;Quais líderes no setor de varejo mostram uma intenção de médio a alto para o Creative Cloud&quot;
* &quot;Encontrar leads com pontuações de intenção contribuídas por downloads de ativos em um webinário&quot;
* &quot;Listar clientes em potencial de alta intenção cuja fonte de atividade principal é o clique em email&quot;
* &quot;Mostrar clientes potenciais com contribuição de intenção somente por visitas da Web, excluindo downloads ou webinars&quot;

### Relatório de perfil de intenção

**Prompt sugerido:** _&quot;Mostrar o perfil de intenção de &lt;lead>&quot;_

Uma visão geral rápida de um cliente potencial: em quais produtos e palavras-chave ele mostra interesse e a pontuação de cada um. Use este relatório assim que um relatório de classificação encontrar um cliente potencial que mereça ser investigado. Ele ajuda você a formar jornadas, personalidades e grupos de compra em torno da intenção real do produto do lead.

Outros prompts:

* &quot;Em quais produtos o &lt;lead> está mais interessado?&quot;
* &quot;No que o &lt;lead> está interessado agora?&quot;
* &quot;Dê-me um resumo de todos os produtos e palavras-chave para os quais o cliente potencial X mostrou intenção&quot;

### Relatório de tendência de intenção

**Prompt sugerido:** _&quot;Mostrar o histórico de pontuações de intenção &lt;lead&#39;s> do &lt;product> nos últimos 30 dias&quot;_

Representa a pontuação de intenção de um lead para um produto ao longo do tempo. Use-o para identificar pontos de inflexão. Por exemplo, uma pontuação que permanece constante por semanas e cai nitidamente indica uma mudança no interesse, não dados irrelevantes. Você pode ajustar o período de 7, 30 ou 100 dias.

Outros prompts:

* &quot;Qual é a intenção de aumento do Acrobat esta semana para o lead X?&quot;
* &quot;Mostrar a tendência da intenção de um cliente potencial este mês&quot;
* &quot;A intenção do lead X para o Acrobat aumentou ou diminuiu este mês?&quot;

### Relatório de comparação de intenção

**Prompt sugerido:** _&quot;Comparar tendências de intenção do Photoshop com o Illustrator em todos os clientes potenciais nos últimos 30 dias&quot;_

Compara a intenção ao longo do tempo para dois leads ou dois produtos, como um gráfico lado a lado mais uma tabela de resumo (pontuação atual, pontuação N dias atrás, delta). O período pode ser ajustado da mesma forma que o relatório de tendências. A intenção pode mudar diariamente, minuto a minuto ou a hora, de modo que uma janela plana curta não significa necessariamente que nada está acontecendo.

Outros prompts:

* &quot;Comparar a intenção da Acrobat e da Photoshop no último trimestre&quot;
* &quot;Comparar o lead X e o propósito do lead Y para o Creative Cloud&quot;
* &quot;Qual tem intenção média mais alta: Photoshop ou Illustrator?&quot;
* &quot;Compare personas para o Acrobat: quem tem a maior taxa de ganhos?&quot;
* &quot;Mostrar intenção lado a lado do Photoshop nos segmentos de Varejo e Finanças&quot;

## Acompanhamento do relatório {#report-follow-up}

Os relatórios de intenção são somente leitura e não têm opção de exportação independente. Para agir de acordo com o que um relatório mostra, use outras habilidades.

* Avisar com _&quot;Listar os principais clientes em potencial de intenção do Creative Cloud.&quot;_ O colega de trabalho usa a habilidade `/analyze-intent` para produzir a lista especificada.

* Avisar com _&quot;Criar uma lista de pessoas usando esta lista.&quot;_ O colaborador entrega o lead definido à [habilidade de criação de público](./audience-creation.md), que cria a lista de pessoas diretamente. Nenhuma etapa manual de exportação ou importação é necessária.
