---
title: Configuração da landing page
description: Espaço reservado
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '971'
ht-degree: 21%

---


# Configuração da landing page

Os administradores devem garantir que as configurações de página de aterrissagem estejam em vigor para os profissionais de marketing que criam e publicam essas páginas. Há dois tipos de configuração necessários para criar páginas de aterrissagem que refletem uma marca e rastreiam o engajamento de maneira eficaz:

* **_Subdomínios_** — Defina onde as páginas de aterrissagem estão hospedadas. Gerencie subdomínios de página de aterrissagem para delegar, configurar ou desdelegar configurações de domínio.
* **_Predefinições_** — Defina configurações reutilizáveis (incluindo subdomínio e outras configurações de canal) para que os profissionais de marketing possam criar e gerenciar páginas de aterrissagem de maneira consistente.

## Subdomínios {#lp-subdomains}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_subdomain_lp_header"
>title="Delegar um subdomínio de página de destino"
>abstract="Configure um subdomínio para o uso da página de destino. Você pode usar um subdomínio que já tenha sido delegado à Adobe ou configurar outro subdomínio."

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_subdomain_lp"
>title="Delegar um subdomínio de página de destino"
>abstract="É necessário configurar um subdomínio de página de destino antes de criar uma predefinição dessa página. É possível usar um subdomínio já delegado à Adobe ou configurar um novo."

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_config_lp_subdomain"
>title="Criar uma predefinição de página de destino"
>abstract="Para criar uma predefinição de página de destino, verifique se há pelo menos um subdomínio de página de destino configurado para selecionar na lista Nome do subdomínio."

Para revisar os subdomínios configurados da página de aterrissagem, vá para **[!UICONTROL Administração]** > **[!UICONTROL Canais]**. Em _[!UICONTROL Páginas de aterrissagem]_ no painel de navegação, selecione **[!UICONTROL Subdomínios de página de aterrissagem]**.

<!-- ![Channel configurations - landing page subdomains](./assets/config-channels-landing-pages-subdomains.png){width="800" zoomable="yes"} -->

A coluna **Status** fornece informações sobre o processo de criação e delegação de subdomínio:

* _[!UICONTROL Rascunho]_: a delegação de subdomínio é salva como rascunho. Clique no nome do subdomínio para retomar o processo de criação.
* _[!UICONTROL Processando]_: o subdomínio está em andamento por meio de várias verificações de configuração, que são necessárias para que ele possa ser usado.
* _[!UICONTROL Sucesso]_: o subdomínio passou pelas verificações com êxito e pode ser usado para entregar mensagens.
* _[!UICONTROL Falha]_: uma ou várias verificações falharam após o envio da delegação de subdomínio.

>[!NOTE]
>
>Antes de [criar predefinições de página de aterrissagem](#lp-presets), você deve configurar os subdomínios a serem usados para páginas de aterrissagem. Você pode usar um subdomínio que já foi delegado à Adobe ou configurar outro subdomínio.

Uma configuração de subdomínio de página de aterrissagem é **comum a todos os ambientes**. Portanto:

* Para acessar e editar subdomínios de páginas de aterrissagem, você deve ter a permissão **[!UICONTROL Gerenciar subdomínios de páginas de aterrissagem]** na sandbox de produção.

* Qualquer modificação em um subdomínio de página de aterrissagem também afeta as sandboxes de produção.

<!-- 
### Use an existing subdomain {#lp-existing-subdomain}

To use a subdomain that is already delegated to Adobe:

1. Click **[!UICONTROL Set up landing page subdomain]**.

    ![](assets/lp_set-up-subdomain.png)

1. For _[!UICONTROL Configuration type]_, choose **[!UICONTROL Use delegated domain]**.

    ![](assets/lp_use-delegated-subdomain.png)

1. Enter the prefix that you want to display in the landing page URL.

    Only alpha-numeric characters and hyphens are allowed.

    >[!CAUTION]
    >
    >Do not use `cdn` or `data` prefixes as these are reserved for internal use. You should also avoid other restricted or reserved prefixes, such as `dmarc` or `spf`.

1. Select a delegated subdomain from the list.

    You cannot select a subdomain that is already used as landing page subdomain.
    
    ![](assets/lp_prefix-and-subdomain.png)

    You cannot use multiple delegated subdomains of the same parent domain. For example, if 'marketing1.yourcompany.com' is already delegated to Adobe for your landing pages, you cannot use 'marketing2.yourcompany.com'. However, when multi-level subdomains are supported for landing pages, you may proceed using a subdomain of 'marketing1.yourcompany.com' (such as 'email.marketing1.yourcompany.com'), or a different parent domain.

    >[!CAUTION]
    >
    >If you select a domain that was delegated to Adobe using the [CNAME method](../configuration/delegate-subdomain.md#cname-subdomain-setup), you must create the DNS record on your hosting platform. To generate the DNS record, the process is the same as when you configure a new landing page subdomain.

1. Click **[!UICONTROL Submit]**.

   The subdomain is displayed in the list with the _[!UICONTROL Processing]_ status. For more on subdomains' statuses, see TBD.

    ![](assets/lp_subdomain-processing.png)

   >[!IMPORTANT]
   >
   >The subdomain is not ready for use until Adobe performs the required checks, which can take **_up to 4 hours_**.

   When the checks are successful, the subdomain is listed with the _[!UICONTROL Success]_ status and it is ready to use for creating landing page presets.
-->

### Configurar um novo subdomínio {#lp-new-subdomain}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_lp_subdomain_dns"
>title="Gerar o registro DNS correspondente"
>abstract="Para configurar um novo subdomínio de página de destino, é necessário copiar as informações do servidor de nomes da Adobe exibidas na interface do Journey Optimizer B2B e colá-las na solução de hospedagem de domínio para gerar o registro DNS correspondente. Quando as verificações são bem-sucedidas, o subdomínio está pronto para ser usado para criar predefinições de página de destino."

1. Clique em **[!UICONTROL Configurar subdomínio da página de aterrissagem]**.

1. Para o _[!UICONTROL Tipo de configuração]_, escolha **[!UICONTROL Adicionar seu próprio domínio]**.

1. Especifique o subdomínio que será delegado.

   >[!IMPORTANT]
   >
   >* Não é possível usar um subdomínio de página de aterrissagem existente.
   >
   >* Letras maiúsculas não são permitidas em subdomínios.

   <!-- ![Landing page subdomain set up](./assets/config-channels-landing-pages-subdomain-setup.png){width="500" zoomable="yes"} -->

   Não é permitido delegar um subdomínio inválido à Adobe. Insira um subdomínio válido de propriedade de sua organização, como marketing.yourcompany.com.

   Para páginas de aterrissagem, os subdomínios de vários níveis são compatíveis. Por exemplo, você pode usar `email.marketing.yourcompany.com`.

1. Copie o registro exibido ou baixe um arquivo CSV e navegue até a solução de hospedagem de domínio para gerar o registro DNS correspondente.

   O registro a ser colocado em seus servidores DNS é exibido.

1. Verifique se o registro DNS foi gerado na solução de hospedagem de domínio.

   Se tudo estiver configurado corretamente, marque a caixa de seleção de confirmação e clique em **[!UICONTROL Enviar]**.

   <!-- ![Landing page subdomain set up with DNS records](./assets/config-channels-landing-pages-subdomain-setup-dns.png){width="500" zoomable="yes"} -->

   Ao configurar um novo subdomínio de página de destino, ele sempre aponta para um registro CNAME.

   Quando a delegação de subdomínio é enviada, o subdomínio é exibido na lista com o status _[!UICONTROL Processando]_.

   >[!IMPORTANT]
   >
   >O subdomínio não está pronto para uso até que o Adobe execute as verificações necessárias, que podem levar **_até 4 horas_**.

   Quando as verificações são bem-sucedidas, o subdomínio é listado com o status _[!UICONTROL Sucesso]_ e está pronto para ser usado para criar predefinições de página de aterrissagem.

   O subdomínio está marcado como _[!UICONTROL Falha]_ se você não criou o registro de validação na solução de hospedagem.

### Cancelar delegação de um subdomínio {#undelegate-subdomain}

1. Em [!DNL Journey Optimizer], cancele a publicação de todas as páginas de aterrissagem associadas ao subdomínio.

1. Se o subdomínio da página de aterrissagem apontar para um registro CNAME, exclua o registro CNAME da solução de hospedagem (não exclua o subdomínio de email original, se houver).

   <!--
    >[!NOTE]
    >
    >A landing page subdomain can point to a CNAME record because it was either an [existing subdomain](#lp-use-existing-subdomain) delegated to Adobe using the [CNAME method](../configuration/delegate-subdomain.md#cname-subdomain-setup), or a [new landing page subdomain](#lp-configure-new-subdomain) that you configured. 
    -->

1. Entre em contato com o representante da Adobe com o subdomínio que deseja cancelar a delegação.

Depois que a Adobe lidar com sua solicitação, a página de inventário de subdomínio não exibe mais o domínio não delegado.

<!-- 
old marketo way for Prime?

A landing page subdomain should help to identify the content type, product name, or campaign, and reinforce the page authenticity. Before you configure the subdomains, define one or more CNAMEs to use for your landing pages. For example:

* **product**.[CompanyDomain].com
* **go**.[CompanyDomain].com
* **signup**.[CompanyDomain].com

In these examples, the first part (in bold) is the `LandingPageCNAME`.

Add a new subdomain for each unique brand URL that you want to host on Adobe Journey Optimizer B2B Edition. You can add a maximum number of 50 subdomains.

>[!IMPORTANT]
>
>Delegating an invalid subdomain to Adobe is not allowed. Make sure you enter a valid subdomain that your organization owns, such as _marketing.yourcompany.com_.

To review your subdomains and add new ones, go to **[!UICONTROL Administration]** > **[!UICONTROL Channels]**. Under _[!UICONTROL Landing Pages]_ in the navigation panel, select **[!UICONTROL Subdomains]**.

![Landing page subdomains](./assets/config-landing-pages-settings.png){width="800" zoomable="yes"}

_To add a landing page subdomain:_

1. Click **[!UICONTROL Add subdomain]** at the top right.

1. In the _[!UICONTROL Subdomain details]_, enter the subdomain information:

   * **[!UICONTROL Subdomain]** - The subdomain URL to use, such as `marketing.yourcompany.com`
   * **[!UICONTROL Default page]** - The URL for the default subdomain page, such as `marketing.yourcompany.com/products`
   * **[!UICONTROL Fallback page]** - The URL for the fallback page to be used if a landing page on the subdomain is not active, such as `marketing.yourcompany.com/expired`

   ![Add landing page subdomain](./assets/config-landing-pages-add-subdomain.png){width="700" zoomable="yes"}

1. Click **[!UICONTROL Save]**.

-->

## Predefinições {#lp-presets}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_config_lp_subdomain_header"
>title="Criar uma predefinição de página de destino"
>abstract="Para criar uma página de destino e aproveitá-la no Journey Optimizer B2B Edition, é necessário criar uma predefinição de página de destino que inclua o subdomínio a ser usado."

Quando os profissionais de marketing criam uma página de aterrissagem, eles devem selecionar uma predefinição de página de aterrissagem para poderem criar a página de aterrissagem e aproveitá-la até [!DNL Journey Optimizer B2B Edition]. A predefinição inclui o subdomínio a ser usado para a página de aterrissagem.

Antes de configurar uma predefinição, verifique se há pelo menos um subdomínio de página de aterrissagem configurado com o status _[!UICONTROL Sucesso]_.

Para revisar as predefinições configuradas da página de aterrissagem, vá para **[!UICONTROL Administração]** > **[!UICONTROL Canais]**. Em _[!UICONTROL Páginas de aterrissagem]_ no painel de navegação, selecione **[!UICONTROL Predefinições de página de aterrissagem]**.

<!-- ![Channel configurations - landing page presets](./assets/config-channels-landing-pages-presets.png){width="800" zoomable="yes"} -->

Clique em qualquer nome de predefinição para acessar os detalhes da predefinição de página de destino.

### Criar uma predefinição de página de destino {#lp-create-preset}

1. Clique em **[!UICONTROL Criar predefinição de página de destino]**.

1. Insira um nome e uma descrição para a predefinição.

   Os nomes devem começar com uma letra (A-Z) e conter apenas caracteres alfanuméricos, sublinhado `_`, ponto `.` e hífen `-` caracteres.

1. Selecione um subdomínio de landing page.

   <!-- ![Landing page preset with name, description, and subdomain](./assets/config-channels-landing-pages-preset-create.png){width="500" zoomable="yes"} -->

   >[!NOTE]
   >
   >Para selecionar um subdomínio, verifique se você configurou anteriormente pelo menos um subdomínio de página de destino.

   As configurações correspondentes ao subdomínio selecionado são exibidas.

1. Você pode selecionar o subdomínio da página de aterrissagem para a **[!UICONTROL URL de rastreamento]** marcando a opção **[!UICONTROL Igual ao subdomínio da página de aterrissagem]**.

   <!-- [Learn more about tracking](../email/message-tracking.md) -->

   <!-- ![Landing page preset with subdomain settings](./assets/config-channels-landing-pages-preset-subdomain-settings.png){width="500" zoomable="yes"} -->

   Por exemplo, se a URL da página de aterrissagem for `pages.mail.luma.com` e a URL de rastreamento for `data.mail.luma.com`, você poderá escolher `pages.mail.luma.com` para ser usado como subdomínio de rastreamento.

   <!-- 
    >[!CAUTION]
    >
    >The selected landing page subdomain is used to specify the **[!UICONTROL Tracking URL]**and **[!UICONTROL Image Delivery URL]** if that subdomain was created using an [existing subdomain](#use-an-existing-subdomain).
    >
    >If the subdomain was created using the [Add your own domain](#configure-a-new-subdomain) option, the primary subdomain (such as the first delegated subdomain) is used instead. We don't have the existing option right now.
    -->

1. Clique em **[!UICONTROL Enviar]** para confirmar a criação da predefinição de página de destino.

   <!--You can also save the preset as draft and resume its configuration later on.-->

   Quando criada, a predefinição de página de aterrissagem é exibida na lista com o status _[!UICONTROL Ativo]_ e está pronta para ser usada na criação de páginas de aterrissagem.