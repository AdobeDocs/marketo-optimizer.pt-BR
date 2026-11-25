---
title: Visão geral do CX Enterprise Coworker no Adobe Marketo Optimizer
description: Saiba como o CX Enterprise Coworker usa as habilidades do Marketo Optimizer para criar e adaptar programas, verificar a prontidão da decisão de IA e chamar as ferramentas MCP.
autotag-review: '2026-11-24T22:43:00.917Z'
TQID: https://experienceleague.adobe.com/V4Kww-NcdfbFxXqWrs7mPq7UYu8AREqDgyfvlMnlURM
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
    internal-label: Chat Interface
  - id: 5229c72e-d79b-574f-a03e-5c4bf48172c3
    internal-label: AI Decisioning
  - id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
    internal-label: Programs
subfeature_v2:
  - id: b9e5c7f3-be30-563c-9e41-cc8ea76e2fee
    internal-label: Skills
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
    internal-label: Artificial intelligence
source-git-commit: 418b81a0a39eca0ca7b537c76da972df7eefd09f
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 2%
---

# [!DNL CX Enterprise Coworker] em [!DNL Adobe Marketo Optimizer] {#coworker-overview}

O Chat [!DNL CX Enterprise Coworker] é uma interface conversacional para concluir tarefas em [!DNL Adobe Marketo Optimizer]. Descreva uma meta em linguagem simples e o [!DNL Coworker] planeja as tarefas, as executa em [!DNL Marketo Optimizer], valida os resultados e fornece o trabalho concluído para sua aprovação.

O [!DNL Coworker] usa habilidades criadas para [!DNL Marketo Optimizer] a fim de orientá-lo pelas tarefas comuns de operações de marketing: criar um novo programa, adaptar um programa existente do [!DNL Marketo Engage] e verificar se os dados estão prontos para a tomada de decisão sobre IA.

[!DNL Coworker] respeita as [[!DNL Marketo Optimizer] permissões](../start/permissions-reference.md) existentes da sua organização. Você só pode realizar ações que você já tenha permissão para realizar, e os administradores controlam quando você tem acesso de gravação. [!DNL Coworker] faz parte do ecossistema do Adobe e não está limitado a [!DNL Marketo Optimizer].

Para obter mais informações, consulte:

* [Visão geral do chat do [!DNL Adobe CX Enterprise Coworker]](https://experienceleague.adobe.com/pt-br/docs/coworker/content/chat/overview)
* [Interface de chat em  [!DNL Marketo Optimizer]](./chat-interface.md)
* [[!DNL Coworker] habilidades em  [!DNL Marketo Optimizer]](./skills.md)

## [!DNL Marketo Optimizer] habilidades em [!DNL CX Enterprise Coworker] {#skills}

Use as seguintes habilidades específicas do produto para criar e adaptar programas ou avaliar a disponibilidade dos dados.

| Habilidade | O que ajuda você a fazer | Exemplo de solicitação |
| --- | --- | --- |
| `program-creation-marketo-optimizer` | Crie um programa de marketing [!DNL Marketo Optimizer] do início ao fim. [!DNL Coworker] guia você desde a meta até um programa criado. | Carregue um resumo da campanha e peça: _Crie um programa usando o resumo anexado._ |
| `adapt-program-marketo-optimizer` | Adapte, migre ou converta um programa existente do [!DNL Marketo Engage] em um programa do [!DNL Marketo Optimizer]. | _Adapte nosso programa Q3 Enterprise Webinar Nurture de [!DNL Marketo Engage] para [!DNL Marketo Optimizer]._ |
| `ai-decisioning-health-marketo-optimizer` | Relate se os dados do seu locatário estão prontos para a decisão sobre IA, a cobertura da história, a riqueza de características e a cobertura de persona. | _Quais dados são usados para a decisão de IA?_ |

### Exemplo de prompt de criação de programa {#program-creation-prompt}

Carregue um resumo ou descreva o programa diretamente. Inclua a audiência, a jornada, o conteúdo e as configurações que você deseja que [!DNL Coworker] use.

O diagrama resume as seções de prompt no exemplo abaixo. Ele mostra como organizar a solicitação, não a ordem em que as pessoas se movem pela jornada.

![Oito seções de prompt de criação de programa: meta do programa, público-alvo, jornada com convites baseados em intenção, conteúdo de email, ativação do LinkedIn, tratamento de registro, acompanhamento pós-evento e configurações.](./assets/coworker-program-creation-prompts.svg){width="800" zoomable="yes"}

Expanda cada seção para exibir o prompt de exemplo.

+++Meta do programa

_Crie um programa de marketing B2B chamado Fórum de Liderança da Experience Cloud - Experience Summit alimentado por IA, que vai de 3 de agosto a 3 de dezembro, usando email e o LinkedIn. O evento acontece no Centro de Inovação da Bay Area às 9h. Iniciar a jornada imediatamente._

+++

+++Público-alvo

_Direcione pessoas com qualquer intenção de produto para a Experience Cloud e uma pontuação de envolvimento maior que 1. Excluir perfis com assinatura cancelada e com suspensão de marketing._

+++

+++Jornada

_Use o Próximo Melhor Caminho para dividir o público por intenção Alta, Medium e Baixa da Experience Cloud. Envie convites personalizados por email ajustados a cada nível de intenção. Mesclar caminhos e aguardar dois dias. Verifique aberturas de email, cliques, participação de conteúdo e registros. Envie uma visualização da agenda para os membros envolvidos; ative os membros não envolvidos no LinkedIn e aguarde dois dias. Mescle caminhos engajados e envie um lembrete de registro final 10 dias antes do evento. Habilitar a Otimização de Tempo de Envio para todos os emails._

+++

+++Conteúdo de email

_Crie três emails: Convite executivo (6 semanas antes do evento), Visualização da agenda (seis semanas antes do evento) e Lembrete de registro final (10 dias antes do evento). Inclua linhas de assunto, pré-cabeçalhos, planos de ação relevantes (Reservar minha vaga, Exibir agenda, Registro completo) e conteúdo personalizado de IA usando a intenção de História de pessoa, Classificação de pessoa, Setor, Interesse na solução, Envolvimento recente e Experience Cloud. Incluir uma imagem do local no convite, mas nenhum banner na visualização da agenda._

+++

+++LinkedIn

_Direcione membros não envolvidos com conteúdo patrocinado, promovendo a transformação da experiência do cliente e a personalização da IA._

+++

+++Registro

_Saia imediatamente dos membros registrados da jornada de convites e envie um email de preparação executiva com tópicos de discussão gerados por IA, uma agenda personalizada, detalhes do local, sessões recomendadas e um link de calendário._

+++

+++Pós-evento

_Encaminhe os participantes para o Programa de Acompanhamento da Liderança da Experience Cloud com um resumo, gravações, recursos e revisão de qualificação de vendas. Envie destaques de no-shows summit, conteúdo sob demanda e convites para eventos futuros._

+++

+++Configurações

_Defina my.replyToEmail como `events@example.com` e my.senderName como Eventos da Experience Cloud. Use um modelo reutilizável no qual apenas a cidade, o local, os tópicos principais do evento e o foco do setor são alterados._

+++

Para obter mais informações sobre como preparar um resumo, consulte [Criar um programa a partir de um resumo](./program-from-brief.md).

## Casos de uso de exemplo {#use-cases}

### Criar um programa após verificar a prontidão dos dados {#check-readiness-create-program}

Um líder de operações de marketing quer saber se o locatário está pronto para a tomada de decisões sobre IA antes de criar um novo programa baseado em conta.

1. Para revisar a cobertura da história, a riqueza de características e a cobertura da persona, execute a [verificação de integridade da decisão de IA](./ai-decisioning-health.md). Por exemplo, pergunte: _Mostrar os dados do Marketo aproveitados para a tomada de decisão sobre IA._
1. Corrigir as lacunas identificadas pelo relatório.
1. Carregar um resumo da campanha e perguntar: _Criar um programa com o resumo anexado._
1. Revise e aprove o programa quando [!DNL Coworker] apresentar o resultado.

O resultado é um relatório de prontidão que identifica deficiências, seguido de um programa baseado em dados que podem apoiar a decisão de IA.

### Mover um programa existente [!DNL Marketo Engage] para [!DNL Marketo Optimizer] {#adapt-program}

Uma equipe de geração de demanda deseja que um programa comprovado seja executado em [!DNL Marketo Optimizer] sem recriá-lo manualmente.

1. Nomeie o programa [!DNL Marketo Engage] a ser adaptado. Por exemplo: _Adapte o programa Q3 Enterprise Webinar Nurture de [!DNL Marketo Engage] para [!DNL Marketo Optimizer]._
1. [!DNL Coworker] mapeia o programa para [!DNL Marketo Optimizer] constrói e sinaliza tudo que não é convertido.
1. Revise o resultado e aprove-o.

O resultado é um programa convertido para sua revisão, além de uma lista de itens que precisam de uma decisão manual.

## [!DNL Marketo Optimizer] ferramentas MCP {#mcp-tools}

As habilidades do [!DNL Coworker] chamam as 37 ferramentas a seguir no servidor MCP (Model Context Protocol) do [!DNL Marketo Optimizer]. Cada nome de ferramenta contém o prefixo `marketo-optimizer__`.

Esta referência abrange ferramentas documentadas por habilidades registradas, incluindo habilidades de suporte usadas durante um workflow. Ele não indica o status de implantação nem a frequência de uso. Os nomes de habilidades nesta tabela seguem a referência da ferramenta e podem ser diferentes dos nomes de habilidades específicas do produto listados acima.

| Ferramenta | Habilidades | Finalidade |
| --- | --- | --- |
| `marketo-optimizer__get_workspace_root_tree` | `program-creation-marketo-optimizer` | Localize a Zona do espaço de trabalho ou a subpasta nomeada de um novo programa. |
| `marketo-optimizer__create_program` | `program-creation-marketo-optimizer` | Crie um programa na Zona ou pasta confirmada. |
| `marketo-optimizer__list_programs` | `program-creation-marketo-optimizer`, `landing-page-authoring` | Procurar programas ou encontrar onde arquivar uma página de aterrissagem. |
| `marketo-optimizer__get_program` | `program-creation-marketo-optimizer` | Ler um programa por ID. |
| `marketo-optimizer__update_program` | `program-creation-marketo-optimizer` | Atualizar metadados do programa, como seu nome. |
| `marketo-optimizer__create_program_token` | `program-creation-marketo-optimizer` | Crie ou corrija um token de programa aprovado. |
| `marketo-optimizer__list_program_tokens` | `program-creation-marketo-optimizer` | Leia os tokens resolvidos de um programa. |
| `marketo-optimizer__create_dynamic_people_list_with_rules` | `program-creation-marketo-optimizer` | Crie uma lista de pessoas vinculada a um programa e gere regras de público-alvo a partir de uma descrição. |
| `marketo-optimizer__list_people_journeys` | `adapt-program`; referência compartilhada do plug-in do canal | Verifique se há uma colisão de nome de jornada de destino, localize uma jornada existente após um resultado não claro ou procure jornadas para trabalho de canal. |
| `marketo-optimizer__create_person_journey` | `program-creation-marketo-optimizer`, `adapt-program`, `channel-content-authoring` | Crie uma jornada vinculada a um programa, inicie uma jornada adaptada ou crie uma jornada ausente para um canal de email. |
| `marketo-optimizer__get_person_journey` | `program-creation-marketo-optimizer`, `adapt-program`; referência compartilhada do plug-in do canal | Leia uma jornada ou sua tela, verifique edições por etapas ou procure uma jornada para trabalho de canal. |
| `marketo-optimizer__update_person_journey` | `adapt-program` | Anexe uma etapa de criação aprovada de cada vez à jornada de destino. |
| `marketo-optimizer__run_person_journey_simulation` | `program-creation-marketo-optimizer` | Validar um fluxo de jornada sem publicar. |
| `marketo-optimizer__run_program_qa` | `program-creation-marketo-optimizer` | Execute uma verificação de preparação somente leitura no programa e em suas jornadas. |
| `marketo-optimizer__create_channel` | `channel-content-authoring`; `program-creation-marketo-optimizer` e `image-to-html` até a entrega | Criar e vincular um canal. Para email, o primeiro call lista templates; o segundo usa o template selecionado para criar e vincular o email. |
| `marketo-optimizer__get_channel` | `channel-content-authoring` | Leia um canal, incluindo, opcionalmente, o assunto do email e o HTML. |
| `marketo-optimizer__list_channels` | `channel-content-authoring` | Navegue pelos canais por tipo, filtrado opcionalmente por nome. |
| `marketo-optimizer__update_channel_content` | `channel-content-authoring`; `image-to-html` até a entrega | Atualize o assunto ou a HTML de um email, incluindo a aplicação do HTML convertido. |
| `marketo-optimizer__image_to_html` | `image-to-html` | Inicie uma conversão assíncrona de design de email e recupere o HTML editável. |
| `marketo-optimizer__list_asset_library_images` | `landing-page-authoring` | Procure imagens de substituição para slots de página de aterrissagem. |
| `marketo-optimizer__add_asset_to_program_or_folder` | `landing-page-authoring` | Registre uma nova landing page no programa ou pasta do Otimizer selecionada. |
| `marketo-optimizer__get_person_story` | `personalization-engine-health` | Leia a história de personalização de uma pessoa por ID numérica. |
| `marketo-optimizer__get_persona_story` | `personalization-engine-health` | Leia a história para obter um nome de pessoa exato. |
| `marketo-optimizer__run_arbitration` | `personalization-engine-health` | Pontuar novamente e selecionar novamente as jornadas para qualificação de pessoas após confirmação explícita. |
| `marketo-optimizer__get_arbitration_summary` | `personalization-engine-health` | Ler estatísticas de resumo para a execução de arbitragem mais recente. |
| `marketo-optimizer__get_arbitration_decisions` | `personalization-engine-health` | Leia decisões por pessoa na última execução de arbitragem. |
| `marketo-optimizer__get_ai_decisioning_health_summary` | `ai-decisioning-health` | Buscar o relatório geral de prontidão do locatário. |
| `marketo-optimizer__get_persona_distribution` | `ai-decisioning-health` | Relatar contagens e porcentagens de persona. |
| `marketo-optimizer__get_people_without_personas` | `ai-decisioning-health` | Relate o número e a proporção de pessoas sem uma persona. |
| `marketo-optimizer__get_person_story_attribute_coverage` | `ai-decisioning-health` | Meça a cobertura da categoria de características e identifique campos preenchidos. |
| `marketo-optimizer__get_person_story_data_completeness` | `ai-decisioning-health` | Relate a riqueza, a integridade e a variação da história por persona. |
| `marketo-optimizer__get_person_story_coverage` | `ai-decisioning-health` | Cobertura de histórias de relatórios, tendências e geração pendente. |
| `marketo-optimizer__get_personalization_story_pipeline_status` | `ai-decisioning-health` | Leia o status do pipeline, o histórico de execução e a duração relatada. |
| `marketo-optimizer__get_person_story_refresh_backlog` | `ai-decisioning-health` | Conte histórias aguardando atualização porque os dados de origem foram alterados. |
| `marketo-optimizer__get_person_intent_signal_coverage` | `ai-decisioning-health` | Meça a intenção do produto, a intenção da palavra-chave e a cobertura da atividade. |
| `marketo-optimizer__get_person_story_activity_coverage` | `ai-decisioning-health` | Relatar campos de envolvimento capturados e agregar tendências de atividade. |
| `marketo-optimizer__get_person_audience_membership_distribution` | `ai-decisioning-health` | Relatar a média e a distribuição de associações de público-alvo por pessoa. |
