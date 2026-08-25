---
title: Pontuações de engajamento de pessoa
description: Calcule as pontuações de engajamento da pessoa para clientes potenciais usando atividades ponderadas e uma janela de pontuação de 30 dias no Marketo Otimizer.
source-git-commit: 75b481faf0d66210329f95c8afabdfa59e7bcb79
workflow-type: tm+mt
source-wordcount: '1515'
ht-degree: 8%

---

# Pontuações de engajamento da pessoa {#engagement-scores}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_person_engagement_score"
>title="Pontuação de engajamento de pessoa"
>abstract="As pontuações de engajamento da pessoa refletem o nível de engajamento de leads individuais com base em suas atividades recentes."

A pontuação de engajamento de uma pessoa é um número que reflete o nível de engajamento de um lead individual. As pontuações são baseadas nas atividades que uma pessoa realiza, em que cada tipo de atividade carrega um valor ponderado. As pontuações são normalizadas em sua instância (locatário) para permitir comparação consistente e insights acionáveis.

O cálculo de pontuação é executado diariamente. Qualquer atividade ponderada pelo envolvimento realizada pela pessoa nos últimos 30 dias contribui para a pontuação. Com essa janela contínua de 30 dias, as ocorrências de atividades mais antigas expiram e as pontuações podem diminuir com o tempo (declínio da pontuação). As pontuações exibidas são arredondadas (por exemplo, uma pontuação de 75,89999 é exibida como 76).

Os dados de pontuação do compromisso estão disponíveis em **[!UICONTROL Relatórios]**.

![Dados de relatório de pontuação do engajamento da pessoa](./assets/engagement-score-reporting.png){width="800" zoomable="yes"}

A pontuação de engajamento da pessoa é um atributo que você pode usar como uma [condição de filtro](#engagement-score-filter) em listas de pessoas e nós de caminho dividido em jornadas de pessoas.

## Atividades usadas para pontuação de engajamento {#activities}

A pontuação de engajamento não é _baseada em acionador_. É um processo diário que avalia a atividade de todos os leads e recalcula as pontuações. As atividades usam _pesos_ para informar a pontuação de acordo com o modelo de ponderação ativa, que determina o quanto cada tipo de atividade contribui para a pontuação geral.

Há um limite de frequência diário de 20 para cada tipo de atividade. Se uma pessoa realizar a mesma atividade mais de 20 vezes em um único dia, a contagem dessa atividade é limitada a 20.

| Nome da atividade | Direção | Descrição | Peso padrão |
|---|---|---|---|
| Participar da conferência | Entrada | Sinal de engajamento presencial de alta intenção | 60 |
| Cliques no email | Entrada | Clique ativo = envolvimento significativo | 30 |
| Clicar em e-mail de vendas | Entrada | Clique ativo em alcance de vendas | 30 |
| Clique em Marketo Email | Entrada | Clique ativo = envolvimento significativo | 30 |
| Envolvido com o Concierge | Entrada | Engajamento ao vivo por meio da ferramenta concierge | 60 |
| Engajado com o bate-papo ao vivo no Concierge | Entrada | Chat ao vivo = alta intenção de compra | 60 |
| Preencher formulário do Marketo | Entrada | Preenchimento do formulário = intenção explícita de lead | 40 |
| Momento interessante | Entrada | Acionador comportamental de alto valor | 60 |
| Novo lead | Entrada | Ponto de entrada — pontuação da linha de base | 30 |
| Abertura de email | Entrada | Engajamento passivo; menor que o clique | 30 |
| Abrir email do Marketo | Entrada | Engajamento passivo; menor que o clique | 30 |
| Abrir email de vendas | Entrada | Engajamento passivo; menor que o clique | 30 |
| Ler mensagem do WhatsApp | Entrada | Leitura passiva; canal de menor peso | 30 |
| Recebeu e-mail de &quot;Encaminhar para amigo&quot; | Entrada | Sinal viral; positivo leve | 30 |
| Responder email de vendas | Entrada | Resposta direta = forte sinal de compra | 40 |
| Solicitar campanha | Entrada | Ação iniciada automaticamente — alta intenção | 30 |
| Solicitar campanha do Marketo | Entrada | Ação iniciada automaticamente — alta intenção | 30 |
| Reunião agendada no Concierge | Entrada | Ação de conversão de intenção mais alta | 60 |

>[!NOTE]
>
>As atividades de pontuação de engajamento são registradas no log de atividades do Marketo Engage de uma pessoa. Você pode acessar esse log na instância associada do Marketo Engage. Para obter mais informações, consulte [Localizar o Log de Atividades de uma Pessoa](https://experienceleague.adobe.com/pt-br/docs/marketo/using/product-docs/core-marketo-concepts/smart-lists-and-static-lists/managing-people-in-smart-lists/locate-the-activity-log-for-a-person){target="_blank"} na documentação do Marketo Engage.

## Lógica de pontuação {#scoring-logic}

O sistema aplica um processo de normalização em várias etapas para produzir uma pontuação consistente em todos os leads na sua instância.

1. Identifique todos os tipos de atividades _ponderadas por engajamento_ que tenham um peso associado e uma cota diária, como cliques em emails, preenchimentos de formulário e presença no evento.

1. Identifique todas as _ações com ponderação de engajamento_ executadas pela pessoa na janela de retrospectiva, que atualmente é de 30 dias.

1. Normalize os pesos do tipo de atividade em todos os tipos de atividade _ponderados por envolvimento_ identificados na etapa 1, ignorando os tipos que não ocorreram na janela de retrospectiva.

   Esta etapa usa _Normalização mín-máx_ e reduz a diluição artificial do peso do tipo de atividade para instâncias que não usam a maioria dos tipos de atividade.

1. Aplique o limite de frequência diária por pessoa e tipo de atividade.

   Essa etapa reduz a influência de atividades de alto volume e de valor mais baixo na pontuação geral.

1. Calcule a pontuação bruta de engajamento somando a atividade diária por tipo de atividade, multiplicando-a pelo peso associado e somando os resultados em todos os dias na janela de retrospectiva.

1. Para estabilizar a variação reduzindo o impacto de valores atípicos, aplique uma _Transformação de Potência_ (Raiz Quadrada).

   Essa transformação reduz a distorção e torna os padrões nos dados mais lineares.

1. Para garantir que as pontuações usem o intervalo completo de 0 a 100, aplique uma transformação de _Normalização em Escala_.

## Filtrar por pontuação de engajamento {#engagement-score-filter}

Você pode usar as pontuações de engajamento da pessoa como filtro ao definir o público-alvo para uma lista de pessoas ou para segmentação em uma jornada de pessoas.

O filtro _[!UICONTROL Pontuação de engajamento da pessoa]_ aparece no painel de filtro na categoria **[!UICONTROL Atributos da pessoa]**.

### Listas de pessoas {#people-lists}

Ao gerenciar membros em uma [lista estática de pessoas](./people-lists.md#static-lists) ou definir regras para uma [lista dinâmica de pessoas](./people-lists.md#dynamic-lists), você pode filtrar por pontuação de engajamento de pessoa para segmentar as pessoas que correspondem aos seus critérios.

![Filtragem de pontuação de envolvimento de pessoa para uma lista de pessoas](./assets/engagement-score-filter-people-list.png){width="700" zoomable="yes"}

**Lista estática — Adicionar membros**

1. Abra a lista estática e clique em **[!UICONTROL Adicionar pessoas]** na parte superior direita.

1. Na caixa de diálogo de filtro, expanda **[!UICONTROL Atributos de pessoas]** e arraste **[!UICONTROL Pontuação de engajamento da pessoa]** para a tela.

1. Na condição de filtro, escolha um operador e insira um valor para corresponder às pontuações que deseja direcionar.

1. Clique em **[!UICONTROL Concluído]** para aplicar o filtro e qualificar as pessoas correspondentes na lista.

**Lista dinâmica — Definir regras de associação**

1. Abra a lista dinâmica e selecione a guia **[!UICONTROL Regras]**.

1. Clique em **[!UICONTROL Editar regras]**.

1. Na caixa de diálogo de filtro, expanda **[!UICONTROL Atributos de pessoas]** e arraste **[!UICONTROL Pontuação de engajamento da pessoa]** para a tela.

1. Na condição de filtro, escolha um operador e insira um valor para corresponder às pontuações que deseja direcionar.

1. Clique em **[!UICONTROL Concluído]** para salvar a regra.

   A associação é atualizada automaticamente à medida que os registros de pessoa são avaliados em relação à regra.

### Jornadas de pessoas {#person-journeys}

Ao configurar a segmentação para uma jornada de pessoa em um nó [_Dividir caminhos_](../marketing/split-merge-paths-nodes.md), você pode usar a pontuação de engajamento de pessoa como um filtro de perfil de pessoa para controlar quais pessoas entram no caminho de jornada.

![Filtragem de envolvimento de pessoa para uma condição de caminho dividido](./assets/engagement-score-filter-split-path.png){width="700" zoomable="yes"}

1. Clique no nó **[!UICONTROL Split paths]** na tela de jornada.

1. No painel de propriedades do nó à direita, clique em **[!UICONTROL Aplicar condição]** ou **[!UICONTROL Editar condição]** para um caminho.

1. Na caixa de diálogo de filtro, expanda **[!UICONTROL Atributos de pessoas]** e arraste **[!UICONTROL Pontuação de engajamento da pessoa]** para a tela.

1. Na condição de filtro, escolha um operador e insira um valor para corresponder às pontuações que deseja direcionar.

1. Clique em **[!UICONTROL Concluído]** para salvar o filtro para o caminho.

## Configurar ponderação de pontuação de engajamento {#configure-weighting}

Em [!DNL Marketo Optimizer], você pode configurar a ponderação da pontuação de engajamento diretamente da [Interface de chat do Colaborador](../agents/chat-interface.md).

Para obter informações sobre modelos de pontuação de envolvimento, faixas de ponderação e pesos da atividade, consulte [Configurar ponderação de pontuação de envolvimento personalizada](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/admin/configurations/engagement-score-weighting).

1. Abra o painel de chat do **[!UICONTROL Colaborador]** no lado esquerdo da tela (ícone de chat).

1. No campo de entrada do chat, digite o comando de barra inclinada seguido da intenção. Por exemplo:

   `/engagement-configuration Configure activity weights for the person engagement score model`

   À medida que você digita `/`, o Coworker exibe uma lista de comandos e habilidades de barra disponíveis. O comando de configuração de engajamento é roteado diretamente para a página Ponderação de engajamento.

   ![Acessar a habilidade de configuração do compromisso no Colaborador](./assets/engagement-score-weighting-coworker-skill.png){width="700" zoomable="yes"}

1. Clique no ícone _Enviar_ (seta para cima) ou pressione Enter.

   O colaborador processa a solicitação e abre uma guia **[!UICONTROL Configuração de envolvimento]** na área de conteúdo principal ao lado do painel de chat.

### Revisar a lista de ponderação de pontuação do envolvimento {#review-weighting-list}

Depois que a guia é aberta, a página _Ponderação de pontuação do engajamento_ exibe todos os modelos de pontuação existentes em uma tabela com as seguintes colunas:

| Coluna | Descrição |
|---|---|
| **Nome** | O nome do modelo (clique para abrir os detalhes) |
| **Status** | Ativo, Rascunho ou Arquivado |
| **Data de criação** | Quando o modelo foi criado |
| **Última atualização** | Carimbo de data/hora de salvamento mais recente |
| **Última atualização por** | Usuário que salvou as últimas alterações |

![Modelos de ponderação de pontuação do compromisso](./assets/engagement-score-weighting-coworker-config.png){width="700" zoomable="yes"}

Em um determinado momento, somente **um** modelo pode estar Ativo. O modelo ativo no momento é aplicado a todos os cálculos de pontuação de engajamento.

### Abrir um modelo de pontuação {#open-scoring-model}

Clique no nome de qualquer modelo na lista para abrir a página de detalhes.

A página detalhada mostra:

* Nome do modelo e selo de status atual (_Ativo_, _Rascunho_ ou _Arquivado_)
* Um campo _Search_ para filtrar a lista de atividades
* A tabela de atividades completa com **[!UICONTROL Atividade de envolvimento]**, **[!UICONTROL Ponderação]**, **[!UICONTROL Última atualização]** e **[!UICONTROL Última atualização por]** colunas

![Detalhes do modelo de ponderação de pontuação do compromisso](./assets/engagement-score-activity-weighting-model.png){width="700" zoomable="yes"}

Para modelos arquivados, **[!UICONTROL Excluir]** e **[!UICONTROL Duplicar]** são exibidos no canto superior direito. Para modelos de rascunho, **[!UICONTROL Ativar]** também é exibido.

### Editar pesos da atividade para um modelo de rascunho {#edit-activity-weights}

Os modelos de rascunho têm opções editáveis de _[!UICONTROL Ponderação]_ para cada atividade de envolvimento. Para alterar um peso:

1. Clique no nome do modelo de rascunho na lista.

1. Na tabela de atividades, localize a atividade de engajamento que deseja atualizar.

1. Clique na seta para baixo **[!UICONTROL Ponderação]** para essa atividade e selecione a faixa de ponderação apropriada (por exemplo, `Important`, `Trivial`, `Minor`, `Normal` e `Vital`).

   As alterações são salvas automaticamente — nenhuma ação Salvar explícita é necessária.

>[!NOTE]
>
>Para editar um modelo ativo ou arquivado, duplique-o para criar um novo modelo de rascunho, depois edite e ative a duplicata. Não é possível editar um modelo ativo no local.

### Ativar um modelo de rascunho {#activate-weighting-model}

Ativar um modelo de rascunho arquiva automaticamente o modelo ativo anteriormente. O modelo recém-ativado aplica-se a todos os cálculos de pontuação de engajamento futuro. Quando seu modelo de rascunho é configurado com os pesos de atividade corretos:

1. Clique no nome do modelo de rascunho na lista.

1. Clique em **[!UICONTROL Ativar]** na parte superior direita.

1. Confirme na caixa de diálogo.

