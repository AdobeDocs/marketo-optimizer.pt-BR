---
title: Adicionar emails ao Jornada
description: Adicione nós de ação de email a jornadas de pessoas e crie novos emails para comunicações direcionadas no Marketo Otimizer.
feature: Email Authoring, Person Journeys
role: User
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '1048'
ht-degree: 7%

---

# Adicionar emails ao jornada

O [!DNL Adobe Marketo Optimizer] traz uma experiência moderna de criação e entrega de email de nível empresarial para os profissionais de marketing B2B.

>[!NOTE]
>
>Se você estiver enviando um email pela primeira vez, verifique se a [capacidade de entrega de emails](../start/email-deliverability.md) e o [canal de email](../admin/email-channel-configuration.md) necessário estão configurados.

<!-- 
* **Email channel configurations** - Manage the sender identity, reply behavior, marketing vs. transactional message types, and tracking.
* **Email deliverability controls** - Set up your email deliverability channel, including subdomain delegation (Fully Delegated and CNAME methods), DMARC, SPF/DKIM auto-configuration, and shared IP pool support.
* **Send Email action** - From a journey, add a _Send email_ action node, including personalization using profile attributes (Handlebars syntax).
* **Visual drag-and-drop email design tools** -  Design your email content with structures, content components, themes, dark-mode support, and reusable visual fragments.
* **Marketo Design Studio assets** — Choose images and assets from a one-time copy of your Marketo Engage asset library directly inside the email canvas.
* **Reusable templates and fragments** — Save common headers, footers, CTAs, and full email layouts and reuse them across journeys.
* **Role-Based Access Control (RBAC)** — Apply granular permissions for creating, editing, approving, and sending email. 
-->

## Limitações atuais {#limitations}

* **Perfis de teste, Simular conteúdo e Enviar prova** não estão disponíveis nesta versão. A renderização do Litmus e os relatórios de spam baseados no SpamAssassin estão no roteiro do GA.
* **A personalização em nível de conta e os dados de objeto personalizado** não estão disponíveis nesta versão. Use atributos de perfil.
* A **migração automatizada do Velocity para Handlebars** dos modelos existentes do Marketo Engage é enviada na data de disponibilidade geral.
* **Comentários e colaboração em emails** (comentários incorporados, @mentions, fluxo de trabalho de solicitação-revisão) enviados em uma versão futura.
* As integrações **AEM Assets, AEM Content Fragments e Adobe Express** estão no roteiro de _Acompanhamento Rápido_.

## Principais conceitos {#key-concepts}

Antes de criar emails para jornadas de pessoas e criar conteúdo de email, analise estes conceitos:

| Conceito | Em [!DNL Adobe Marketo Optimizer] |
| ------- | ---------------------- |
| **_Espaço de design de email_** | A tela visual e as ferramentas de design usadas para compor conteúdo de email. Ele inclui componentes de layout de arrastar e soltar, templates, fragmentos, temas e um editor de personalização. |
| **_Modelo_** | Um layout de email reutilizável que está disponível para criar um novo email. Ele pode ser um modelo integrado fornecido pelo Adobe ou um modelo personalizado criado pela sua equipe. |
| **_Fragmento visual_** | Um bloco reutilizável de conteúdo (como cabeçalho, rodapé, CTA, aviso de isenção legal) que pode ser inserido em vários emails. A atualização de um fragmento propaga a alteração para cada email que o utiliza. |
| **_Tema_** | Uma predefinição de estilo reutilizável (cores, tipografia, espaçamento, estilos de botão) aplicada em um email. |
| **_token do Personalization_** | Uma expressão Handlebars — por exemplo, `{{profile.firstName}}` — resolvida no momento do envio usando os dados de perfil de cada recipient. |
| **_Ação Enviar email_** | O nó de ação de jornada que usa uma configuração de canal e conteúdo de email para entregar um email. |

## Adicionar um email de uma jornada

Para enviar email de uma jornada, [adicione um nó _Faça uma ação_](action-nodes.md#add-an-action-node) e configure-o para enviar email.

1. Na tela de jornada, clique no ícone **+** e selecione **[!UICONTROL Realizar uma ação]**.

1. Nas propriedades do nó à direita, defina a ação como **[!UICONTROL Enviar email]**.

   ![Executar uma ação - Enviar email](./assets/person-action-node-send-email.png){width="500"}

1. Escolha a fonte do e-mail:

   * **Criar/editar email** - Escolha esta opção para definir o conteúdo do email, incluindo a linha de assunto, as informações do remetente e o corpo do email no espaço de design do email.

   * **[!UICONTROL Usar um email personalizado para IA]** - (_Não disponível para o Beta_) Escolha esta opção para refinar um email gerado para IA no espaço de design de email. Esses emails são otimizados para que os clientes da caixa de entrada assistida por IA fundamentem seus resumos e respostas em suas ofertas e planos de ação.

1. Clique em **[!UICONTROL Criar email]**.

1. Na caixa de diálogo _[!UICONTROL Criar email]_, digite um **[!UICONTROL Nome]** exclusivo (obrigatório) e uma **[!UICONTROL Descrição]** (opcional).

   ![Caixa de diálogo Criar email](./assets/email-channel-create-email-dialog.png){width="400"}

1. Clique em **[!UICONTROL Criar]**.

Para a [otimização de tempo de envio](email-send-time-optimization.md) opcional, configure o nó de ação de jornada depois de criar o email.

## Definir as propriedades e ações do email {#define-email-properties}

A página de e-mail é aberta quando você cria um e-mail para um nó _[!UICONTROL Enviar e-mail]_. Você também pode acessar esta página após a criação do email clicando em **[!UICONTROL Editar email]** nas propriedades do nó à direita.

1. (Opcional) Na guia **[!UICONTROL Propriedades]**, digite qualquer informação descritiva que você deseja capturar para o email.

1. Selecione a guia **[!UICONTROL Ações]** e conclua as configurações funcionais do email:

   * **[!UICONTROL Email]** - Selecione ou crie uma **[!UICONTROL Configuração de canal de email]** para usar.

     Esse é o conjunto reutilizável de configurações de entrega de email que define a identidade do remetente, o endereço de resposta, o subdomínio, o pool de IPs, o tipo de email (marketing ou transacional) e o rastreamento. Clique no ícone _Exibir_ para examinar as configurações da configuração selecionada.

     Os administradores criam configurações em [Configuração do canal de email](../admin/email-channel-configuration.md).

   * **[!UICONTROL Regras de negócio]** - (Opcional) Aplique regras de limite ou período de silêncio à sua ação de email selecionando um conjunto de regras.

     Para obter mais informações sobre regras de negócios e como definir e ativar conjuntos de regras para comunicações de canal, consulte [_Regras de negócios_](../admin/business-rules.md).

   * **[!UICONTROL Rastreamento de ação]** - Marque as caixas de seleção das ações que deseja rastrear para o email.

   ![Canal de email - guia Ações](./assets/email-channel-actions-tab.png){width="600" zoomable="yes"}

1. Clique em **[!UICONTROL Editar conteúdo]** ou selecione a guia **[!UICONTROL Conteúdo]**.

1. Insira o texto da **[!UICONTROL Linha de assunto]** que você deseja exibir no campo de assunto do email.

   Clique no ícone _Personalizar_ ( ![Ícone Personalizar](../assets/do-not-localize/icon-personalize.svg) ) para usar um token de personalização no campo.

1. (Opcional) Marque a caixa de seleção **[!UICONTROL Otimizar o tamanho do HTML]** para reduzir o tamanho do HTML de email durante o processo de publicação.

   Isso ajuda a evitar o corte de emails em clientes como o Gmail, que truncam mensagens com mais de 100 KB. Consulte [_Otimizar o tamanho do HTML de email_](#optimize-html-size) para obter mais informações.

1. Clique em **[!UICONTROL Editar corpo do email]** para acessar as ferramentas de design visual e começar a [criar seu conteúdo](../content/email-authoring.md).

   Como alternativa, você pode clicar em **[!UICONTROL Editor de código]** para codificar seu próprio conteúdo em HTML simples. Se você tiver um HTML existente para reutilizar em seu design de email, é possível copiá-lo e colá-lo no editor.

### Verificar alertas {#alerts}

[!DNL Adobe Marketo Optimizer] apresenta problemas no canto superior direito da página de email. Resolva todos os erros antes de ativar a jornada. Os avisos são somente recomendações.

**Erros** (impedir ativação de jornada):

* O nome do remetente está vazio
* Linha de assunto ausente
* O conteúdo do email está vazio

**Avisos** (recomendações):

* O link para opção de não participação não está presente no corpo do email
* A versão de texto do HTML está vazia
* Links vazios detectados
* Email excede 100 K

## Otimizar o tamanho do HTML de email {#optimize-html-size}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_email_minification"
>title="Reduzir tamanho do HTML"
>abstract="Ative esta opção para compactar o código HTML do seu email durante a publicação, removendo espaços em branco desnecessários, recuos e comentários não essenciais. Isso ajuda a evitar o corte de emails em clientes como o Gmail, que truncam mensagens com mais de 100 KB."

O [!DNL Marketo Optimizer] permite compactar a versão do HTML de email durante o processo de publicação removendo espaços em branco, recuos e comentários não essenciais desnecessários. Manter o tamanho pequeno do HTML ajuda a:

* Evite **recorte de email** — alguns clientes, como o Gmail, truncam mensagens com mais de ~100 KB, impedindo que os destinatários visualizem o conteúdo completo.
* Melhore o **tempo de carregamento do email** na caixa de entrada do destinatário.
* Melhore a **deliverability** e reduza o uso da largura de banda.

Essa otimização não é aplicada automaticamente — você deve habilitá-la na guia _[!UICONTROL Conteúdo]_.

<!-- ![](assets/email-optimize-html-size.png) -->

>[!IMPORTANT]
>
> A redução de tamanho do HTML é aplicada somente no momento da publicação.

A otimização é segura para o cliente de email:

* Preserva comentários condicionais do MSO/Outlook.
* Isso não altera seu conteúdo, imagens ou vídeos reais.

>[!NOTE]
>
>A redução no tamanho do email depende da estrutura original do HTML do email. Se o conteúdo já estiver compacto ou a carga do email for muito grande, a redução pode ser mínima e talvez não impeça totalmente o recorte em todos os casos.

<!-- 
Proof and simulate workflows are not available in this release. See [Current limitations](#limitations).

### Test HTML size optimization {#optimize-html-proof}

If you have enabled the [HTML size optimization](#optimize-html-size) option, you can evaluate its impact before publishing when sending proofs. Follow the following steps.

1. In the email design space, click the _Issues_ icon on the top right. If the rendered email size exceeds 100 KB, a message is displayed to warn you that this may cause truncation in some email clients.

1. Click **[!UICONTROL Simulate content]**.

1. To test the optimized version, click the **[!UICONTROL Send proof]** button and select the **[!UICONTROL Optimize HTML size]** option. This will send a proof with the reduced HTML size to your test recipients.

    >[!NOTE]
    >
    >This setting is independent from the email editor — the proof reflects what you select in the proof, regardless of whether the option is enabled or disabled in the email itself.

1. Select the test recipients and click **[!UICONTROL Send proof]**.

1. Back in the **[!UICONTROL Simulate]** screen, click the **[!UICONTROL View Proof]** button.

1. Click the _Information_ icon next to the status of the proof.

   The optimization details are displayed in a pop-up window, including the original HTML size, the optimized HTML size, and the size reduction percentage.
    
    Use this information to validate the optimized output and confirm the email stays within the recommended 100 KB threshold before publishing.

-->
