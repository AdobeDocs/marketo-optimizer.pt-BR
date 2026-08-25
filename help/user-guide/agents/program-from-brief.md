---
title: Criar um programa a partir de um resumo
description: Use a habilidade de Criação de programas no Marketo Otimizer para criar programas, tokens, listas de pessoas e jornadas de um resumo da campanha.
source-git-commit: 75b481faf0d66210329f95c8afabdfa59e7bcb79
workflow-type: tm+mt
source-wordcount: '1110'
ht-degree: 4%

---

# Criar um programa a partir de um resumo

Em [!DNL Adobe Marketo Optimizer], o [_programa_](../marketing/programs.md) é o contêiner de nível superior para jornadas, listas de pessoas, tokens e configurações em uma campanha. Na [interface de chat](./chat-interface.md), a habilidade de Criação de programa cria essa estrutura inteira de ponta a ponta do seu resumo — o próprio programa, subpastas, tokens, listas de pessoas e jornadas de pessoas — em uma conversa guiada.

* **Habilidade** - `program-creation`
* **Chamada** - Carregue um resumo e insira _Criar um programa a partir deste resumo_ / _Criar um programa a partir do resumo_ ou descrever a campanha diretamente
* **Lê/grava em** - [!DNL Marketo Optimizer]; também lê a configuração de tipo de programa do seu locatário

## Upload breve

Clique no ícone _Anexar_ na entrada do chat para carregar o arquivo e descrever o que você deseja. O texto do resumo é extraído e entregue ao colaborador como contexto (você verá um indicador &quot;Resumo da campanha carregado: nome do arquivo (NkB)&quot; no chat).

### Tipos de arquivo compatíveis

| Formato | Comportamento |
|---|---|
| `.txt`, `.md` | Ler diretamente no navegador |
| `.pdf`, `.docx`, `.xlsx`, `.json`, `.csv` | Enviado para o serviço de extração de texto de back-end |

Um arquivo com um nome contendo *brief* é automaticamente marcado como um resumo de campanha; caso contrário, o Colaborador o infere do contexto.

### Limite de tamanho

O texto breve é truncado em aproximadamente 30.000 caracteres (tokens de aproximadamente 7,5 mil) antes de chegar ao Co-worker. Curvas muito longas são cortadas nesse ponto (indicado por uma nota `(truncated to 29KB)`). Coloque os detalhes essenciais da campanha no início.

## Conteúdo breve recomendado

A entrada de fluxo lê o resumo das seguintes entradas — inclua o máximo possível:

* Nome do programa e uma breve descrição/finalidade
* Sinal de tipo de programa (como feiras, eventos, webinários, apresentações, conferências ou atividades promocionais)
* Critérios de público-alvo para as listas de pessoas
* Design da jornada — contagem, critérios de entrada, pontos de contato/tempo e uma data de ativação
* Tokens (valores reutilizáveis, como data do evento, local, linha de assunto)

O colaborador solicita tudo o que estiver faltando antes da criação.

## Fases de criação

A habilidade é executada em três fases: **ENTRADA → APROVAR → COMPILAÇÃO**. Nada é criado até que você aprove.

### Entrada

O colaborador extrai o seguinte do resumo e solicita qualquer item ausente:

* Nome do programa
* Pasta primária (o padrão é a raiz do espaço de trabalho, se não especificada)
* Descrição
* Tipo de programa (deduzido de texto breve quando possível)
* Tokens a serem criados (nome, tipo, valor)
* Critérios de público-alvo da lista de pessoas
* Jornadas — contagem, critérios de entrada, pontos de contato, data de ativação

### Aprovar

O colaborador apresenta um resumo de confirmação antes de continuar:

`I'll create {program} in folder {id}, with {N} token(s), {N} dynamic people list(s), and {N} journey(s). Shall I proceed?`

Nenhuma ferramenta de criação será chamada até que você responda com um claro prosseguimento (como _prosseguir_, _prosseguir_, _compilar_, _aprovado_ e _sim_).

### Build

As etapas de criação são executadas em uma ordem fixa; cada uma depende das IDs produzidas pela etapa anterior.

| Etapa | Descrição | Ferramentas | Output |
|---|---|---|---|
| **1. Pasta** | Resolve a pasta pai por nome ou usa a raiz do espaço de trabalho; é possível criar uma nova subpasta | `getRootTree`, `browseFolders`, `createFolder` | Nome da pasta + ID |
| **1.5. Tipo de programa** | Procura tipos de programas de locatários e escolhe a correspondência para o resumo | `browseProgramTypes` | Nome do tipo + `programTypeId` |
| **2. Programa** | Cria o Programa na pasta resolvida, vinculado ao tipo escolhido | `createProgram` | Nome do programa, ID, tipo |
| **3. Tokens** | Cria cada token `my.*` no programa | `createProgramToken` | Nomes dos tokens |
| **4. Listas de pessoas** | Gera regras baseadas em atributos a partir de critérios de público-alvo e cria a lista dinâmica de pessoas | `generate_ruleset`, `createSmartListWithRules` | Nome da lista + `smartListId` |
| **5. Jornadas** | Cria cada jornada de pessoa com um nó de entrada de público-alvo de pessoa conectado à lista Etapa 4 | `create_journey` | Jornada nomes, IDs |
| **6. Publicar** | Publica ou agenda a jornada se uma data de publicação estiver definida e confirmada | `publish_journey_with_dates` | Jornada online/agendada |
| **7. QA** | Visualização de validação opcional e verificação completa de controle de qualidade | `qa_program_preview`, `qa_program` | Relatório de aprovação/reprovação/avisos |

**_Dependências de etapa:_**

* A ID do programa (Etapa 2) é necessária antes que tokens, listas ou jornadas possam ser anexados.
* O `smartListId` da Etapa 4 é passado para `create_journey` na Etapa 5 — omiti-lo deixa o nó de entrada de público-alvo da jornada vazio.
* O prompt de jornada sempre começa _Start com um nó de público-alvo Person como o ponto de entrada_ para garantir um nó de entrada preenchido.

## Ativos de saída

### Programa

O contêiner de nível superior. Sua exibição detalhada expõe as seguintes guias:

| Tabulação | Conteúdo |
|---|---|
| **Visão geral** | Nome, descrição, tipo de programa, status, local da pasta, carimbos de data e hora |
| **Atributos** | Campos personalizados definidos pelo tipo (somente se o tipo de programa os ativar) |
| **Tokens** | `my.*` tokens com escopo para este programa |
| **Jornadas** | Jornadas contidas no programa |

### Tokens

Valores `my.*` reutilizáveis com escopo para o programa (por exemplo, `my.eventDate`). Cada uma tem um tipo — um de `text`, `date`, `rich text`, `score` ou `number` — e um valor. Eles são resolvidos dentro de emails e conteúdo dentro do escopo do programa.

### Lista de pessoas

Uma lista dinâmica (inteligente) de pessoas criada a partir de critérios de público-alvo por meio de regras geradas com base em atributos, criada no programa.

### Jornada

Uma jornada de pessoa que começa com um nó de entrada de público-alvo Pessoa vinculado à lista de pessoas Etapa 4, seguida pelos pontos de contato do resumo (por exemplo, _enviar email de boas-vindas após 1 dia, acompanhamento após 3 dias_). Se uma data de publicação for definida, a jornada poderá ser publicada imediatamente ou programada.

## Resolução de tipo de programa

Os programas estão **permanentemente vinculados** a um tipo de programa definido pelo locatário na criação — isso não pode ser alterado posteriormente. O fluxo resolve o tipo explicitamente via `browseProgramTypes` em todos os casos.

| Caso | Comportamento |
|---|---|
| **Vários tipos disponíveis** | Corresponde uma breve redação a um tipo (como tradeshow/booth/expo = *Tradeshow*/*Event*; webinar = *Webinar*/*Event*; Nurture/drip = *Nurture*; sem sinal claro = *Default*). Se nenhuma correspondência for encontrada, o Colaborador listará os tipos e as tarefas disponíveis. |
| **Locatário somente padrão** | Usa o *Padrão* e observa que um administrador pode adicionar [tipos de programas](../admin/program-types.md) personalizados. |
| **Nenhum tipo configurado** | Paradas — a criação falharia. Solicita que um administrador provisione tipos de programas antes de tentar novamente. |

## Padrões

| Configuração | Padrão |
|---|---|
| **Pasta** | Raiz do Workspace (se nenhuma pasta for especificada) |
| **Tipo de programa** | *Padrão* (se não houver um sinal curto e nenhuma seleção manual) |
| **Atributos do Personalization** | Persona derivada, Intenção derivada, Nível de envolvimento incluído por padrão (opção de não participação disponível) |
| **Publicação** | Não automático para datas de publicação futuras — anotado como uma etapa manual `ACTIVATE journey by {date}`; publicar imediatamente somente ao iniciar agora e confirmar |
| **Portão de aprovação** | Nenhum ativo é criado antes de uma aprovação explícita |

## Limitações

| Limitação | Detalhe |
|---|---|
| **Limite de comprimento curto** | ~30 mil caracteres; resumos truncados perdem conteúdo à direita — coloque os essenciais em primeiro lugar |
| **Tipo de programa imutável** | Não pode ser alterado após a criação; verifique o tipo correto antes da aprovação |
| **Campos internos obrigatórios** | `parent` e `programTypeId` estão sempre definidos; omitir `parent` causa acesso negado; omitir tipo silenciosamente retorna para *Padrão* |
| **A Jornada exige a lista de pessoas** | O `smartListId` da Etapa 4 é obrigatório para a Etapa 5; o fluxo impõe isso |
| **Associação de lista assíncrona** | As listas estáticas (de critérios) são preenchidas ao longo de vários minutos, não instantaneamente |
| **Tratamento de erros** | Falhas de ferramenta são relatadas com o erro exato; o colega de trabalho solicita a confirmação da entrada e tenta novamente |
| **Colisões de nome** | Não resolvido automaticamente — um nome diferente será solicitado |
| **Escopo** | Somente Marketo Otimizer; [!DNL Marketo Engage] usuários devem usar as habilidades de criação/planejamento de programas separadas |


## Verificação de controle de qualidade

Depois que a criação for concluída, o Colaborador oferece:

> &quot;Gostaria que eu executasse uma verificação de controle de qualidade para validar tudo antes do lançamento?&quot;

Confirme para executar `qa_program_preview` seguido por `qa_program`. O processo retorna um relatório de verificações aprovadas, com falha e avisos, juntamente com as próximas etapas recomendadas.
