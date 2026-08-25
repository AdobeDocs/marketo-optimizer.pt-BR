---
title: Decisão sobre IA
description: Entenda a decisão de IA no Marketo Otimizer, a camada de inteligência por trás do controle de tráfego do jornada, o próximo melhor caminho, a otimização de tempo de envio e outros recursos que substituem regras estáticas pela automação orientada por resultados.
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 2%

---


# Decisão sobre IA

O AI Decisioning é a camada de inteligência por trás do Adobe Marketo Otimizer. Em vez de pré-construir cada ramificação como uma regra estática, o AI Decisioning avalia continuamente o contexto de um perfil, incluindo a associação à jornada, o histórico de engajamento, as pontuações de intenção e o comportamento em tempo real, para determinar a próxima melhor ação ou caminho para essa pessoa.

Essa avaliação contínua move a orquestração de regras estáticas para a automação orientada por resultados: em vez de definir cada condição antecipadamente, você descreve o resultado desejado e o sistema determina como chegar lá para cada pessoa.

## Recursos {#capabilities}

O AI Decisioning é composto pelos seguintes recursos:

| Recurso | O que decide |
|---|---|
| [controle de tráfego de Jornada](../marketing/journey-traffic-control.md) | Em qual jornada uma pessoa deve estar agora. Quando uma pessoa se qualifica para mais de uma jornada, o controle de tráfego de jornada a redireciona no momento em que seu perfil ou comportamento muda, em vez de deixá-la em um caminho que não cabe mais. |
| [Próximo melhor caminho](../marketing/next-best-path.md) | O caminho mais adequado para uma pessoa em uma jornada. Em vez de codificar as condições do filtro, você descreve a intenção em linguagem natural e o sistema direciona cada pessoa para o melhor caminho correspondente no momento certo. |
| [Otimização de tempo de envio](../marketing/email-send-time-optimization.md) | A melhor janela de envio para cada recipient, com base no engajamento histórico, em vez de uma programação fixa para todos. |
| Conteúdo contextual | Variantes de email personalizadas geradas automaticamente a partir de um resumo de conteúdo, para uso como um único ativo de email personalizado no jornada. _Em breve._ |
| [Brand Concierge](https://experienceleague.adobe.com/pt-br/docs/brand-concierge/content/home){target="_blank"} | Roteamento e resposta conversacional em tempo real, como bate-papo e assistência ao vivo. O Brand Concierge exige direitos de produto adicionais. |

Alguns desses recursos resolvem problemas diferentes na mesma jornada. O controle de tráfego de jornada decide qual jornada ganha prioridade quando várias jornadas estão competindo para engajar a mesma pessoa ao mesmo tempo. Os outros recursos decidem o que acontece depois que uma pessoa já está em uma jornada.

## Dividir caminhos e o próximo melhor caminho {#split-paths-next-best-path}

[Os caminhos divididos](../marketing/split-merge-paths-nodes.md) permitem definir ramificações de jornada com condições de filtro explícitas: se uma pontuação estiver acima de um limite, envie uma pessoa para um caminho abaixo, caso contrário, envie outra para outro. Essa lógica baseada em regras é precisa e totalmente auditável, mas cada nova condição requer uma nova ramificação.

O nó [Próximo melhor caminho](../marketing/next-best-path.md) aplica a decisão de IA ao mesmo problema. Em vez de um limite fixo, o modelo avalia o envolvimento, a persona, o interesse do produto e o estágio do funnel juntos, prevê o melhor resultado para cada pessoa e seleciona o caminho ideal automaticamente.

## Entradas de dados {#data-inputs}

A decisão sobre IA baseia-se nas seguintes categorias de dados:

| Categoria | Exemplos |
|---|---|
| Demográfico e firmográfico | Cargo, setor e tamanho da empresa |
| Psicográfico | Pontuação, urgência e prioridade do lead |
| Engajamento | Pontuação, nível, tendência, última atividade e canal |
| Intenção | Produto ou intenção de palavra-chave, agrupado em compartimentos alto, médio ou baixo |
| Persona | Função na negociação, cargo e persona |

## Cadência de avaliação {#evaluation-cadence}

O AI Decisioning usa dois cronogramas de avaliação diferentes. O perfil subjacente de uma pessoa é recalculado em um lote noturno. A decisão em si é aplicada em tempo real em todas as interações, usando o que o perfil noturno mais recente indicar. Assim, a parte contínua da decisão de IA descreve o momento da decisão, não a taxa de atualização do perfil.

## Medidas de proteção e regras {#guardrails-rules}

As regras só abrangem condições que alguém escreveu explicitamente. Quando a realidade fica fora dessa árvore, como uma persona híbrida ou uma combinação de sinal que ninguém antecipou, as regras não fazem nada até que alguém adicione uma nova ramificação. A decisão de IA classifica cada pessoa continuamente e gera uma melhor ação baseada em confiança, portanto, lida com combinações para as quais ninguém explicitamente programado e melhora à medida que vê mais resultados, o que uma regra nunca faz.

As regras são explicáveis e instantâneas para a auditoria, enquanto a decisão sobre IA tem pontuação de confiança em vez de determinística. Por esse motivo, as regras continuam a ser a melhor ferramenta quando:

* Um limite de conformidade rígida nunca deve ser ultrapassado, como a supressão de contatos recusados.
* Ainda não há volume ou histórico suficiente para um modelo aprender.
* Cada decisão deve ser totalmente explicada mediante pedido.

A maioria das configurações maduras é executada em conjunto: regras como medidas de proteção e decisões de IA que lidam com tudo no meio.

## Benefícios {#benefits}

* Menos complexidade de jornada manual, com menos ramificações de regras a serem mantidas.
* Experiências mais relevantes sem criar centenas de regras.
* Maior eficiência na qualificação.
* Identificação mais rápida do próximo melhor engajamento para cada perfil.

>[!BEGINSHADEBOX]

**Escopo futuro: contexto de conta e grupo de compras**

Hoje não disponível no Marketo Otimizer. A decisão sobre IA deve ir além do perfil individual para:

* Contexto da conta — Sinais no nível da empresa e da conta como uma entrada de decisão.
* Sinais do grupo de compra — função no status do negócio, tomador de decisão ou profissional e engajamento agregado a todos envolvidos em uma decisão de compra.
* Orquestração de jornadas no nível da conta — decisões de roteamento e conteúdo tomadas para a conta ou grupo de compras como uma unidade, com o controle de tráfego de jornadas coordenado entre as várias pessoas envolvidas.

>[!ENDSHADEBOX]
