---
title: Permissões do produto
description: Lista de referência das permissões do Experience Platform que controlam o acesso aos recursos do Marketo Optimizer, com descrições e permissões recomendadas para usuários administradores, com acesso completo e somente leitura.
TQID: https://experienceleague.adobe.com/Q4HnGxPkiE0dsZUjIgPvVJHgs0dPwLJiOKVSL1edS4Y
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3cf5f37e-e87e-5179-812b-53ce05d7eebb
    internal-label: Setup
  - id: a659ad61-de21-559d-a901-02e2fb329ff5
    internal-label: Administration
subfeature_v2:
  - id: b6434e31-d7bb-5416-960c-1c77bb1a2e8d
    internal-label: User Access
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
autotag-review: '2026-10-20T17:03:48.312Z'
source-git-commit: a33f749c32631dcd77ecf2892bdc3b1a5e06cd66
workflow-type: tm+mt
source-wordcount: '1556'
ht-degree: 3%
---
# Permissões do produto

As permissões a seguir controlam o acesso aos recursos em [!DNL Adobe Marketo Optimizer]. Adicione-as a funções na área _[!UICONTROL Permissões]_ de [!DNL Adobe Experience Platform]. Para obter informações detalhadas sobre como criar funções e atribuí-las a usuários, consulte [_Acesso e permissões de usuário_](./user-management.md).

As três últimas colunas mostram as permissões recomendadas para cada um dos [tipos de usuários sugeridos](#suggested-user-types): Administrador, Todos os usuários com acesso e Usuário com acesso somente leitura. Uma marca de seleção (✔) significa que a permissão é recomendada para esse tipo de usuário, e um traço (-) significa que não é. Ajuste as recomendações para se ajustarem à sua organização.

>[!IMPORTANT]
>
>O acesso [!DNL Marketo Optimizer] exige que você habilite uma sandbox específica provisionada usando a seguinte convenção de nomenclatura: `Mktoaep` + prefixo de assinatura [!DNL Marketo Engage]. Por exemplo, se o prefixo de assinatura vinculado do [!DNL Marketo Engage] for _AcmeAssoc_, a sandbox necessária para o acesso do [!DNL Marketo Optimizer] será _MktoepAcmeAssoc_. Adicione esta sandbox a todas as funções.

>[!NOTE]
>
>Você deve ser um administrador do sistema para ver o bloco _[!UICONTROL Permissões]_ no Experience Platform.

Algumas permissões se aplicam a recursos que ainda não estão disponíveis no produto. Os administradores podem adicionar essas permissões agora para que os usuários tenham o acesso aplicável quando os recursos estiverem disponíveis.

## Tipos de usuário sugeridos {#suggested-user-types}

Use as recomendações de permissão nas tabelas desta página como ponto de partida para as funções que você cria. Estas são sugestões para cada tipo de usuário. Ajuste-os para se ajustarem à sua organização.

| Atributo | Admin | Todos os usuários de acesso | Usuário de acesso somente leitura |
| --- | ----- | --------------- | --------------------- |
| **Quem é ele** | Pessoas que configuram e gerenciam o [!DNL Marketo Optimizer] para a sua equipe. | Profissionais de marketing e operadores que trabalham no [!DNL Marketo Optimizer] todos os dias. | Pessoas que precisam ver [!DNL Marketo Optimizer], mas não precisam mudar nada, como executivos, analistas e auditores. |
| **O que eles podem fazer** | Tudo, incluindo configurações de instalação e administração. | Use todos os recursos: jornadas, programas, conteúdo, listas, relatórios e o assistente. | Exiba jornadas, programas, conteúdo, listas e relatórios e faça perguntas ao assistente. |
| **Permissões a serem atribuídas** | Todas as permissões desta página (selecione **[!UICONTROL Adicionar tudo]** no editor de funções). | As permissões com um ✔ na coluna _Todo acesso_ das tabelas desta página. | As permissões com um ✔ na coluna _Somente Leitura_ das tabelas desta página. |
| **Não incluído** | – | <li>Configurações de administração<li>Configurações de canal, incluindo configurações de email, predefinições de formulário, configurações de página de aterrissagem e predefinições e configurações do WhatsApp<li>Tipos de programas (exibir e gerenciar) | <li>Criando, editando, excluindo, publicando ou exportando (todas as _permissões Gerenciar_ e _Publicar_, exceto o acesso a chat)<li>Ativação de públicos para destinos<li>Configurações de administrador e de canal, incluindo a visualização de configurações de email e predefinições de formulário<li>Exibição de tipos de programas |
| **Grupo de usuários sugerido** | Grupo de administradores do Marketo Optimizer | Grupo de usuários do Marketo Optimizer | Grupo de usuários somente leitura do Marketo Optimizer |
| **Função sugerida** | Administrador do Marketo Optimizer | Todos os usuários de acesso do Marketo Optimizer | Usuário de acesso somente leitura do Marketo Optimizer |

Para obter o procedimento para criar esses grupos e funções, consulte [Criar grupos de usuários e funções para os tipos de usuários sugeridos](./user-management.md#create-suggested-roles).

## Conteúdo e ativos {#content-assets}

| Categoria | Permissão | Descrição | Admin | Todos os acessos | Somente leitura |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| Assets B2B | Gerenciar Assets B2B | Criar, editar e excluir arquivos de ativos. | ✔ | ✔ | – |
| | Gerenciar emails B2B | Criar, editar e excluir mensagens de email. | ✔ | ✔ | – |
| | Gerenciar Forms B2B | Criar, editar e excluir formulários. | ✔ | ✔ | – |
| | Gerenciar fragmentos B2B | Criar, editar e excluir fragmentos de conteúdo. | ✔ | ✔ | – |
| | Gerenciar página de aterrissagem B2B | Criar, editar e excluir páginas de destino. | ✔ | ✔ | – |
| | Gerenciar exportação de mensagens B2B | Exportar relatórios de mensagens na seção _Email_. | ✔ | ✔ | – |
| | Gerenciar modelos B2B | Criar, editar e excluir modelos de conteúdo. | ✔ | ✔ | – |
| | Gerenciar webinários B2B | Criar, editar e excluir webinários interativos. | ✔ | ✔ | – |
| | Publicar Forms B2B | Publicar formulários para uso em landing pages. | ✔ | ✔ | – |
| | Publicar fragmentos B2B | Publicar fragmentos de conteúdo para uso em modelos, emails e landing pages. | ✔ | ✔ | – |
| | Publicar página de aterrissagem B2B | Publicar páginas de destino. | ✔ | ✔ | – |
| | Exibir Assets B2B | Visualize a biblioteca do Assets e os detalhes do arquivo do ativo. | ✔ | ✔ | ✔ |
| | Visualizar emails B2B | Exibir mensagens de email. | ✔ | ✔ | ✔ |
| | Exibir Forms B2B | Exibir formulários. | ✔ | ✔ | ✔ |
| | Visualizar fragmentos B2B | Visualizar a lista de fragmentos de conteúdo e os detalhes. | ✔ | ✔ | ✔ |
| | Exibir página de aterrissagem B2B | Exibir páginas de aterrissagem. | ✔ | ✔ | ✔ |
| | Visualizar modelos B2B | Exibir a lista de modelos de conteúdo e os detalhes. | ✔ | ✔ | ✔ |
| | Exibir webinários B2B | Ver webinários interativos. | ✔ | ✔ | ✔ |

## Configuração e administração de canais {#channels-admin}

| Categoria | Permissão | Descrição | Admin | Todos os acessos | Somente leitura |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| Configurações do administrador B2B | Gerenciar configurações de administrador B2B | Definir configurações de administração, como conexões de gerenciamento de ativos digitais, repositórios de ativos e eventos. | ✔ | – | – |
| Configurações do canal B2B | Gerenciar configurações de canais B2B | Acesso ao item de menu _Canais_ na navegação à esquerda e em todas as operações de configuração de canal. | ✔ | – | – |
| | Gerenciar configurações de email B2B | Defina as configurações de email. Essas configurações são necessárias antes que os usuários possam enviar emails. | ✔ | – | – |
| | Gerenciar predefinição de Forms B2B | Criar, editar e excluir predefinições de formulário. | ✔ | – | – |
| | Gerenciar configurações de página de aterrissagem B2B | Defina as configurações da página de aterrissagem, como subdomínios. | ✔ | – | – |
| | Gerenciar predefinições B2B do WhatsApp | Criar, exibir e excluir predefinições de mensagem do WhatsApp e configurações de SMS associadas. | ✔ | – | – |
| | Gerenciar configurações B2B do WhatsApp | Configurar os parâmetros do canal do WhatsApp. | ✔ | – | – |
| | Publicar predefinição de Forms B2B | Publicar predefinições de formulário. | ✔ | – | – |
| | Exibir configurações de email B2B | Exibir configurações de email (subdomínios, registros PTR, pools de IP, listas de supressão, listas de propagação, planos de aquecimento de IP). | ✔ | – | – |
| | Visualizar predefinição de Forms B2B | Visualizar predefinições de formulário. | ✔ | – | – |

## Jornadas, programas e pastas {#journeys-programs}

| Categoria | Permissão | Descrição | Admin | Todos os acessos | Somente leitura |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| Tokens da pasta B2B | Gerenciar tokens da pasta B2B | Criar, editar e excluir tokens em pastas. As alterações se aplicam a tudo na pasta, portanto, atribua isso separadamente de _Gerenciar pastas B2B_. | ✔ | ✔ | – |
| | Visualizar tokens da pasta B2B | Exibir tokens definidos em pastas. | ✔ | ✔ | ✔ |
| Pastas B2B | Gerenciar pastas B2B | Criar, editar e excluir pastas. | ✔ | ✔ | – |
| | Exibir pastas B2B | Exibir pastas. | ✔ | ✔ | ✔ |
| Jornadas B2B | Gerenciar controle de tráfego de Jornada B2B | Configurar o controle de tráfego do jornada, incluindo a simulação do efeito. | ✔ | ✔ | – |
| | Gerenciar Jornadas de pessoa B2B | Acesso à lista _Jornadas de pessoas_ e a todas as operações de jornada de pessoas. | ✔ | ✔ | – |
| | Publicar Jornadas de pessoa B2B | Publicar jornadas da pessoa. | ✔ | ✔ | – |
| | Exibir controle de tráfego de Jornada B2B | Exibir configurações de controle de tráfego do jornada. | ✔ | ✔ | ✔ |
| | Exibir relatórios de Jornada de pessoa B2B | Exibir relatórios de jornada de pessoa, incluindo o relatório de _Indivíduo de Jornada de pessoa_. | ✔ | ✔ | ✔ |
| | Exibir Jornadas de pessoa B2B | Acesso somente leitura à lista de _Jornadas de pessoas_ e detalhes da jornada. | ✔ | ✔ | ✔ |
| Tokens de programa B2B | Gerenciar tokens do programa B2B | Crie, edite e exclua tokens em programas e tipos de programas. | ✔ | ✔ | – |
| | Exibir tokens do programa B2B | Exibir tokens definidos em programas e tipos de programas. | ✔ | ✔ | ✔ |
| Tipos de programa B2B | Gerenciar tipos de programas B2B | Criar, editar e excluir tipos de programas de marketing. | ✔ | – | – |
| | Visualizar tipos de programas B2B | Exibir tipos de programas de marketing. | ✔ | – | – |
| Programas B2B | Gerenciar programas B2B | Criar, editar e excluir programas de marketing. | ✔ | ✔ | – |
| | Exibir programas B2B | Exibir programas de marketing. | ✔ | ✔ | ✔ |

## Públicos, intenção e destinos {#audiences-intent}

| Categoria | Permissão | Descrição | Admin | Todos os acessos | Somente leitura |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| Destinos B2B | Ativar destinos B2B | Ative públicos para destinos B2B. | ✔ | ✔ | – |
| | Gerenciar destinos B2B | Criar, editar e excluir destinos B2B. | ✔ | ✔ | – |
| | Exibir destinos B2B | Acesso somente para visualização a destinos B2B. | ✔ | ✔ | ✔ |
| Configuração de intenção B2B | Gerenciar configuração de intenção B2B | Crie, edite e exclua configurações de intenção. | ✔ | ✔ | – |
| | Exibir configuração de intenção B2B | Exibir configurações de intenção (modelos de ponderação de intenção). | ✔ | ✔ | ✔ |
| Regras da organização B2B | Gerenciar regras da organização B2B | Criar, editar e excluir regras de organização. | ✔ | ✔ | – |
| | Exibir regras de organização B2B | Exibir regras da organização. | ✔ | ✔ | ✔ |
| Listas de pessoas B2B | Gerenciar listas de pessoas B2B | Crie, edite e exclua listas de pessoas e gerencie a associação a listas. | ✔ | ✔ | – |
| | Exibir Listas de pessoas B2B | Exibir listas de pessoas estáticas e dinâmicas. | ✔ | ✔ | ✔ |

## Relatórios, laboratórios e bate-papo {#reports-labs-chat}

| Categoria | Permissão | Descrição | Admin | Todos os acessos | Somente leitura |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| Experiência de conversa B2B | Gerenciar experiência de conversa B2B | Acesse o painel de bate-papo e o assistente. As ações no painel também exigem a permissão do recurso correspondente. Por exemplo, criar uma jornada requer _Gerenciar Jornadas de pessoas B2B_. Consulte [Permissões de chat](#chat-permissions). | ✔ | ✔ | ✔ |
| Labs B2B | Gerenciar laboratórios B2B | Ative e configure os recursos do Labs. | ✔ | ✔ | – |
| | Exibir laboratórios B2B | Veja os recursos do Labs que estão disponíveis e ativados. | ✔ | ✔ | ✔ |
| Relatório B2B | Visualizar relatórios incorporados B2B | Exiba os relatórios na guia _Relatórios_. | ✔ | ✔ | ✔ |
| | Exibir relatórios de intenção B2B | Exibir relatórios de intenção. | ✔ | ✔ | ✔ |

## Permissões de chat {#chat-permissions}

As permissões de chat seguem as permissões no nível de recurso. [!DNL Coworker for Marketo Optimizer] verifica todas as habilidades ou ações no chat com a mesma permissão que o recurso precisa fora do chat: _Gerenciar_ permissões para criar, editar ou publicar e _Exibir_ permissões para habilidades somente leitura. Se um usuário não tiver a permissão do recurso, [!DNL Coworker] não poderá executar essa ação para ele. Por exemplo, criar uma jornada requer _Gerenciar Jornadas de Pessoas B2B_, e listar formulários requer _Exibir Forms B2B_.

<!--
_Manage B2B Conversational Experience_ gives access to the [!DNL CX Coworker] chat panel, but it does not grant access to any feature functions.

Per wiki: 
Update 10/02: We are no longer mapping b2b-conversational-experience read or write to any tools. It was decided that chat will be available for all users without permissions, but what they can do within the chat (i.e. tools they can use) will be defined by other permissions.
-->

## Permissões de destinos externos {#external-destinations-permissions}

Para fornecer acesso a destinos externos para usuários no [!DNL Marketo Optimizer], as seguintes permissões são necessárias. As colunas seguem as mesmas recomendações para cada tipo de usuário descrito em [Tipos de usuário sugeridos](#suggested-user-types).

| Categoria | Permissão | Descrição | Admin | Todos os acessos | Somente leitura |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| Painéis | Gerenciar painéis padrão | Adicione atributos personalizados que ainda não estão no data warehouse. | ✔ | ✔ | – |
| | Ver Painéis de Controle Padrão | Acesso somente para visualização aos painéis _Perfis_, _Destinos_ e _Segmentos_. Também permite o acesso a _Painéis_ na navegação à esquerda. | ✔ | ✔ | ✔ |
| Destinos | Ativar destinos | Ativar dados para destinos ativos. _Exibir Destinos_ ou _Gerenciar Destinos_ também são necessários. | ✔ | ✔ | – |
| | Ativar segmento sem mapeamento | Ative públicos para destinos existentes sem a etapa de mapeamento. Os usuários podem adicionar e remover públicos-alvo em workflows de ativação, mas não podem adicionar ou remover atributos ou identidades mapeadas. _Exibir Destinos_ também é necessário. | ✔ | ✔ | – |
| | Criação de destino | Destinos de autor usando o Experience Platform Destination SDK. | ✔ | ✔ | – |
| | Gerenciar e ativar destino do conjunto de dados | Visualize, crie, edite e desative fluxos de exportação de conjunto de dados e ative dados para conjuntos de dados. _Exibir Destinos_ também é necessário. | ✔ | ✔ | – |
| | Gerenciar destinos | Exibir, criar e excluir conexões de destino e contas de destino. | ✔ | ✔ | – |
| | Exibir destinos | Exiba os destinos disponíveis na guia _Catálogo_ e os destinos autenticados na guia _Procurar_. | ✔ | ✔ | ✔ |
| Governança de dados | Gerenciar rótulos de uso de exclusão B2B | Exibir, criar e excluir rótulos de uso de dados (DULE) aplicados a conjuntos de dados e esquemas. | ✔ | ✔ | – |
| | Gerenciar políticas de uso de dados | Exibir, criar, editar e excluir políticas de uso de dados. | ✔ | ✔ | – |
| | Exibir políticas de uso de dados | Acesso somente para visualização para políticas de uso de dados pertencentes à sua organização. | ✔ | ✔ | ✔ |
| Ingestão de dados | Gerenciar fontes | Exibir, criar, editar e desativar fontes. | ✔ | ✔ | – |
| | Exibir fontes | Exibir fontes disponíveis na guia _Catálogo_ e fontes autenticadas na guia _Procurar_. | ✔ | ✔ | ✔ |
| Gerenciamento de perfil | Gerenciar configurações do perfil | Exibir e editar todas as configurações de perfil. | ✔ | ✔ | – |
| | Exibir configurações do perfil | Acesso somente para visualização a todas as configurações do perfil. | ✔ | ✔ | ✔ |

<!-- 

## Planned permissions {#planned-permissions}

The following permissions are for features that are not yet available in [!DNL Marketo Optimizer]. Adobe Marketo Qualifier permissions are not currently enforced. The estimated enforcement date is November 2026. Accounts and buying groups are targeted for delivery in Q1 2027.

| Category | Permission | Description | Admin | All Access | Read Only |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| Marketo Qualifier Configurations | Manage Marketo Qualifier Configurations | Create, edit, and delete Marketo Qualifier configurations. | ✔ | – | – |
| | View Marketo Qualifier Configurations | View Marketo Qualifier configurations. | ✔ | ✔ | ✔ |
| Marketo Qualifier Outbound | View Marketo Qualifier Outbound | View Marketo Qualifier outbound workflows and outbound reporting. | ✔ | ✔ | ✔ |
| Marketo Qualifier Research | Manage Marketo Qualifier Research | Use and manage research capabilities. | ✔ | ✔ | – |
| | View Marketo Qualifier Research | View research: conversational interface, prospect view, and account and lead research. | ✔ | ✔ | ✔ |
| B2B Account Lists | Manage B2B Account Lists | Create, edit, and delete account lists, including adding, removing, and importing accounts. | ✔ | ✔ | – |
| B2B Buying Groups | Manage B2B Buying Groups | Create, edit, and delete buying groups. | ✔ | ✔ | – |
| | Manage B2B Role Templates | Manage the role templates used in buying groups. | ✔ | ✔ | – |
| | Manage B2B Solution Interests | Manage the solution interests used in buying groups. | ✔ | ✔ | – |
| | Manage B2B Stages | Manage buying group stages. | ✔ | ✔ | – |
| | View B2B Buying Groups | View buying groups. | ✔ | ✔ | ✔ |

-->
