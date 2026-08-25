---
title: Criar públicos-alvo para programas
description: Use a habilidade Criação de público no Marketo Otimizer para criar listas de pessoas, adaptar as Smart Lists da Marketo Engage e editar regras de lista no chat.
source-git-commit: c00dc1d3f3028ece56905f9f1018605147b0ac20
workflow-type: tm+mt
source-wordcount: '1464'
ht-degree: 0%

---

# Criar públicos-alvo para programas

Em [!DNL Adobe Marketo Optimizer], [_listas de pessoas_](../audiences/people-lists.md) definem o público-alvo para jornadas de pessoas — como listas dinâmicas baseadas em filtros que são atualizadas automaticamente ou listas estáticas com associação fixa. Na [interface do chat](./chat-interface.md), a _Criação de Público-Alvo_ [habilidade](./skills.md) cria, adapta e edita listas de pessoas por meio de uma conversa guiada.

* **Habilidades** - `audience-creation` e `people-list-comparison`
* **Chamada** - Descreva os critérios de público diretamente, carregue uma Lista Inteligente [!DNL Marketo Engage] ou nomeie uma lista existente para editar
* **Leituras/gravações em** - [!DNL Marketo Optimizer]; lê [!DNL Marketo Engage] ao adaptar Smart Lists

## Fluxos de trabalho compatíveis {#workflows}

O Colaborador oferece suporte a três fluxos de trabalho de criação de público-alvo e determina qual deles se aplica à sua solicitação. Se a intenção for ambígua, ele pergunta antes de continuar.

| Fluxo de trabalho (WRK) | Quando usá-lo | Exemplo de prompt |
|---|---|---|
| **Criar do zero** | Você deseja uma nova lista de pessoas definida por critérios ou associação. | _&quot;Crie uma lista dinâmica de VPs de Marketing em empresas SaaS na América do Norte.&quot;_ |
| **Adaptar uma Lista Inteligente [!DNL Marketo Engage]** | Você já tem uma lista inteligente [!DNL Marketo Engage] ou campanha inteligente e deseja uma lista de pessoas equivalente. | _&quot;Adapte esta lista inteligente do Marketo a uma lista de pessoas.&quot;_ (anexar o ativo) |
| **Editar uma lista existente** | Você deseja adicionar ou substituir as regras em uma lista que já possui. | _&quot;Adicione uma regra à minha lista de &#39;Avaliações da Empresa&#39; para uma pontuação de lead superior a 50.&quot;_ |

## Criar uma lista de pessoas do zero {#create-from-scratch}

Antes de gerar qualquer coisa, Coworker confirma todos os quatro itens a seguir. Ele solicita qualquer item que esteja faltando — em uma única mensagem.

1. **Regras/critérios** — uma descrição em linguagem simples de quem pertence à lista.
1. **Nome** — Como chamar a lista.
1. **Local** — Em qual programa a lista deve estar. Forneça um nome de programa e o Colaborador o encontra; se houver várias correspondências, ele solicita que você escolha.
1. **Tipo** — Dinâmico (baseado em filtro, atualização automática) ou estático (associação fixa). Isso é obrigatório — o colega de trabalho não adivinhará; se você não especificar, ele perguntará.

### Listas dinâmicas {#dynamic-lists}

Para listas dinâmicas, o Colaborador sugere proativamente a inclusão de atributos de personalização para tornar o direcionamento mais rico. Estes atributos estão **_incluídos por padrão — você opta por não participar_**:

| Atributo | Por que ajuda |
|---|---|
| **Pessoa Derivada** | Persona compradora inferida por IA para direcionamento de conteúdo com base em persona. |
| **Intenção Derivada** | Sinais de intenção de compra inferidos que são exibidos nas contas do mercado. |
| **Nível de participação** | Nível de envolvimento calculado que prioriza os contatos envolvidos. |

Informe ao Colaborador se você deseja remover qualquer um desses itens antes de continuar.

### Listas estáticas {#static-lists}

* **Estático, sem critérios** — A lista é criada vazia, pronta para você adicionar membros manualmente.
* **Estático a partir dos critérios (um instantâneo)** — o Colaborador cria o conjunto correspondente e copia essas pessoas em. O público é assíncrono — O parceiro confirma que a lista foi criada, mas observa que pode levar alguns minutos para que as pessoas apareçam. Ele não irá alegar que a lista está pronta imediatamente.

## Revisar cartão {#review-card}

Nada é criado até que você o aprove. Após descrever seus critérios, o Coworker apresenta um cartão interativo _Análise de Criação da Lista de Pessoas_ (para adaptações de listas [!DNL Marketo Engage], o cartão é intitulado _Análise de Conversão da Lista de Pessoas_).

Cada linha no cartão representa uma condição:

| Coluna | Significado |
|---|---|
| **Requisitos** (ou o nome da lista [!DNL Marketo Engage] para adaptações) | Sua solicitação original ou o filtro de origem do Marketo. |
| **(regra)** | A regra baseada em atributos real gerada para essa condição. |
| **Incluir** | Uma caixa de seleção para manter ou eliminar essa regra. |

**Níveis de confiança:**

* **As linhas** de alta confiança são claramente correspondidas e verificadas por padrão.
* **Baixa confiança** linhas (mapeamentos aproximados ou qualquer outro sinalizador) são mostradas com um indicador de aviso e são desmarcadas por padrão.
* As linhas que o sistema não pôde mapear mostram **&quot;Nenhum equivalente encontrado&quot;** — elas não têm regra e permanecem desmarcadas.

Um _Resumo de Conversão_ conta _N Alta Confiança_ e _N Baixa Confiança_, com uma dica: as regras de baixa confiança estão desmarcadas por padrão; marque-as para incluir ou descreva a alteração desejada no chat.

**Ações do cartão:**

* **Continuar** — Cria a lista usando apenas as regras verificadas.
* **Descreva as alterações desejadas no chat** — Preenche a entrada previamente com _&quot;Desejo alterar: &quot;_ para que você possa refinar; o Colaborador regenera e mostra um cartão novo, mantendo as regras que você já aprovou.

Você também pode digitar um acompanhamento a qualquer momento (por exemplo, _&quot;também restrito a empresas com mais de 500 funcionários&quot;_) e o Colaborador regenera o cartão.

## Mapeamento de atributos {#attribute-mapping}

Quando você descreve os critérios, o Colaborador traduz cada condição em um atributo de nível de pessoa real e conhecido. Três resultados podem aparecer no cartão Revisão:

1. **Correspondente (alta confiança)** — Sua condição mapeia diretamente para um atributo (por exemplo, _&quot;email é acme.com&quot;_ mapeia para o atributo `email`). Marcado por padrão.
1. **Aproximado (baixa confiança)** — O atributo mais próximo disponível difere no nome ou no modelo de dados (por exemplo, um filtro _Quantidade_ do Marketo aproximado como _Pontuação de lead_). Mostrado com uma nota explicando a diferença; desmarcado por padrão.
1. **Não encontrado** — A condição não pôde ser mapeada para nenhum atributo conhecido. Mostrado como _&quot;Nenhum equivalente encontrado&quot;_; nenhuma regra é gerada.

É por isso que uma lista que você descreve pode voltar com menos regras do que as condições especificadas — condições sem correspondência são exibidas explicitamente em vez de serem descartadas silenciosamente. Se os critérios importantes forem exibidos como &quot;não encontrado&quot;, reescreva-os usando o nome real do atributo e as tentativas do colaborador.

>[!NOTE]
>
>Se você estiver mapeando colunas de planilha para campos (um cartão de Mapeamento de Campo com _Coluna Source_, _Campo de Destino_, uma porcentagem de confiança e uma lista de _Colunas não Mapeadas_), esse será o fluxo de importação principal, não a criação de público-alvo. Consulte a [habilidade de importar clientes em potencial](./skills.md#audiences-people).

## Editar regras de uma lista existente {#edit-rules}

Quando você solicita a alteração de regras em uma lista já existente, o Colaborador estabelece qual lista e qual modo de edição:

* **Adicionar/acrescentar** (padrão para _&quot;adicionar regras&quot;_, _&quot;adicionar mais regras&quot;_) — as novas regras são mescladas com as existentes.
* **Substituir** (padrão para _&quot;substituir regras&quot;_, _&quot;alterar regras para&quot;_) — novas regras substituem todas as regras existentes na lista.

O Colaborador resume o que será aplicado e declara claramente se está adicionando ou substituindo e solicita que você confirme antes de confirmar. Após a aplicação, ele relata a contagem total de regras e quantas foram adicionadas ou substituídas.

>[!NOTE]
>
>As edições usam um caminho com reconhecimento de mesclagem, de modo que uma operação &quot;adicionar&quot; nunca substitui silenciosamente as regras existentes.

## Sobreposição de público-alvo {#overlap}

Peça ao Colaborador para comparar duas listas de pessoas (por exemplo, _&quot;Mostrar a sobreposição entre &#39;Webinar do 3º trimestre&#39; e &#39;Contas da Empresa&#39;&quot;_) e ele renderiza um cartão _Sobreposição da Lista de Pessoas_:

* Um selo de cabeçalho mostrando a contagem: **&quot;{N} em comum.&quot;**
* Uma linha de estatísticas com a contagem total de membros de cada lista e a sobreposição como **&quot;X% de A · Y% de B.&quot;**
* Uma tabela de membros das pessoas nas duas listas, com uma coluna **Nome** e uma segunda coluna que você pode orientar — **Email** (padrão), **Empresa** ou **Cargo**, dependendo do que você solicitou.
* Clique em qualquer nome para abrir essa pessoa no espaço de trabalho.
* Se não há sobreposição, o cartão diz tão claramente: _&quot;Não há membros em comum entre essas duas listas.&quot;_

**Limitações:**

| Limite | Detalhe |
|---|---|
| **Tamanho da tabela** | Mostra até 200 membros; além disso, observa _&quot;Mostrando 200 de N — peça-me para refinar a consulta para restringir os resultados.&quot;_ |
| **Computação de sobreposição** | Calculado no endereço de email; as pessoas sem um email são excluídas da interseção. |
| **Tamanho da lista** | Lê aproximadamente os primeiros ~1.000 membros de cada lista. Para listas maiores, o Colaborador informa que os resultados são parciais. |
| **Listas dinâmicas de rascunhos** | Não pode ser comparado — uma lista que não foi publicada não tem um segmento ativo. O colega de trabalho solicita que você publique primeiro ou use uma lista estática. |

## Validação de controle de qualidade {#qa-validation}

Depois de criar ou atualizar uma lista, o Colaborador oferece: _&quot;Deseja que eu verifique se a lista está configurada corretamente?&quot;_ Se você aceitar, ela buscará novamente a lista e relatará as seguintes verificações:

| Marcar | Resultado |
|---|---|
| Lista encontrada no programa/pasta correto | Aprovado/reprovado |
| A contagem de filtros corresponde ao que foi aplicado | _N_ filtros / incompatibilidade |
| Atributos do Personalization presentes (se incluídos) | Presente/ausente |
| O nome da lista corresponde ao que você solicitou | Aprovado/reprovado |
| Contagem estimada de membros | _count_ ou N/A |

## Limitações {#limitations}

| Limitação | Detalhe |
|---|---|
| **Adaptação da lista estática de[!DNL Marketo Engage]** | Você não pode adaptar uma lista estática [!DNL Marketo Engage] (ou um email ou outro ativo que não seja de filtro) em uma lista de pessoas. As listas estáticas são IDs de membro explícitas e não podem ser expressas como filtros; Em vez disso, o colega de trabalho solicita uma Smart List ou uma Campanha Inteligente. |
| **Filtros baseados em atividade e associação** | Ao adaptar de [!DNL Marketo Engage], filtros como _Email Aberto_, _Página da Web Visitada_, _Formulário Preenchido_, _Membro da Lista_ e _Membro da Campanha Inteligente_ não têm equivalente na lista de pessoas e retornam como &quot;Nenhum equivalente encontrado.&quot; |
| **Condições no nível da empresa** | Traduzido para o atributo de nível de pessoa mais próximo, quando possível (as listas de pessoas operam em atributos de pessoa) e sinalizado de baixa confiança quando o ajuste está solto. |
| **Lógica AND/OR profundamente aninhada** | Lógica aninhada complexa pode ser reduzida a AND/OR de nível superior; o colaborador observa isso quando isso ocorre. |
| **Colisões de nome** | Não resolvido automaticamente — se o nome for usado, o Co-worker solicitará um diferente, em vez de anexar silenciosamente um sufixo. |
| **Aprovação necessária** | O colega de trabalho não criará ou modificará uma lista até que você clique em **[!UICONTROL Continuar]**, confirme ou forneça uma visão geral clara (_&quot;aprovado&quot;_, _&quot;parece bom&quot;_, _&quot;criar&quot;_). |
| **População de instantâneos estáticos** | A associação a listas estáticas criadas a partir de critérios preenche mais de alguns minutos — não instantaneamente. |

