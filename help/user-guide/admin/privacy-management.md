---
title: Gerenciamento de privacidade
description: Saiba como cumprir com o GDPR, CCPA e outras regulamentações de privacidade no Marketo Otimizer e enviar solicitações usando o Adobe Privacy Service.
feature: Setup
role: Admin
topic_v2: id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 75b481faf0d66210329f95c8afabdfa59e7bcb79
workflow-type: tm+mt
source-wordcount: 630
ht-degree: 2%

---


# Gerenciamento de privacidade {#privacy-management}

O [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/pt-br/docs/experience-platform/privacy/home){target="_blank"} fornece uma API RESTful e uma interface para ajudar você a gerenciar solicitações de dados do cliente. Com o [!DNL Adobe Privacy Service], você pode enviar solicitações para acessar e excluir dados pessoais dos clientes por meio dos aplicativos corporativos do Adobe CX, facilitando a conformidade automatizada com as regulamentações legais e organizacionais de privacidade.

O [!DNL Adobe Marketo Optimizer] fornece essas ferramentas de privacidade para que você possa atender aos requisitos globais de proteção de dados. Use [!DNL Privacy Service] para enviar e gerenciar solicitações de acesso e exclusão para dados que [!DNL Marketo Optimizer] coleta e armazena.

Você pode enviar solicitações individuais para acessar e excluir dados do consumidor de [!DNL Adobe Marketo Optimizer] de duas maneiras:

* A interface do usuário do [!DNL Privacy Service]
* A API [!DNL Privacy Service]

## Regulamentos de privacidade compatíveis {#regulations}

As ferramentas de privacidade do [!DNL Marketo Optimizer] ajudam você a cumprir os regulamentos até o [!DNL Privacy Service]. Cada regulamento se aplica se você mantiver dados de pessoas que residem na região associada.

Para obter uma lista atualizada das regulamentações compatíveis, consulte [_Visão geral das regulamentações de privacidade_](https://experienceleague.adobe.com/en/docs/experience-platform/privacy/regulations/overview){target="_blank"} na documentação do Privacy Service.

## Tipos de solicitação {#access-and-delete-requests}

[!DNL Marketo Optimizer] dá suporte a dois tipos de solicitação de privacidade:

* **Acesso aos dados** - Uma pessoa pode solicitar uma confirmação de que seus dados pessoais estão sendo processados e receber uma cópia eletrônica gratuita desses dados.
* **Exclusão de dados** - Também chamado de _direito a ser esquecido_, uma pessoa pode solicitar que você apague seus dados pessoais e interrompa o processamento.

## Exibir e gerenciar solicitações de privacidade {#view-manage-requests}

>[!BEGINSHADEBOX]

![Ícone de Permissões do AEP](../assets/do-not-localize/icon_permissions-outline.svg) Essas etapas exigem o perfil de produto [!DNL Privacy Service] e as [permissões a seguir para a função de usuário atribuída no Experience Platform](../start/user-management.md#permissions):

* **[!UICONTROL Permissões do Privacy Service]** - `Privacy Read Permission` e `Privacy Write Permission`
* **[!UICONTROL Governança de dados]** - `View Privacy Console`

Consulte [_Gerenciar permissões do Privacy Service_](https://experienceleague.adobe.com/en/docs/experience-platform/privacy/permissions){target="_blank"} no Guia do [!DNL Privacy Service] para obter informações mais detalhadas.

>[!ENDSHADEBOX]

Para exibir os trabalhos de solicitação de privacidade em [!DNL Marketo Optimizer], expanda **[!UICONTROL Privacidade]** e selecione **[!UICONTROL Solicitações]**.

Use a opção **[!UICONTROL Tipo de Regulamentação]** na parte superior direita para alterar a página exibida para a regulação em que você deseja gerenciar trabalhos ou enviar solicitações.

![Trabalhos de solicitação de privacidade, selecione o tipo de regulamento](./assets/privacy-requests.png){width="800" zoomable="yes"}

### Enviar uma solicitação {#submit-a-request}

1. Clique em **[!UICONTROL Criar solicitação]**.

1. Para o **[!UICONTROL Tipo de Trabalho]**, selecione o tipo de solicitação:

   * **[!UICONTROL Acesso]**

     Quando você envia uma solicitação de **_acesso_** que inclui [!DNL Marketo Optimizer], [!DNL Privacy Service] retorna:

     * [!DNL Marketo Engage] atividade associada ao cliente potencial.
     * Atividade [!DNL Marketo Optimizer] associada à pessoa ou conta.

   * **[!UICONTROL Excluir]**

     Quando você envia uma solicitação de **exclusão** para [!DNL Marketo Engage] e [!DNL Marketo Optimizer], os seguintes registros são removidos:

     * O lead associado em [!DNL Marketo Engage].
     * Registros de pessoa e conta criados em [!DNL Marketo Optimizer].
     * Histórico de conversas com colegas de trabalho que faz referência às informações pessoais da pessoa.

1. Para **[!UICONTROL Produtos]**, selecione **[!UICONTROL Marketo]**.

   ![Criar solicitação de privacidade de acesso ao GDPR para o Marketo Engage e o Marketo Otimizer](./assets/privacy-request-create-gdpr.png){width="450" zoomable="yes"}

   Esta seleção inclui dados de [!DNL Marketo Optimizer] e da instância [!DNL Marketo Engage].

1. Role para a parte inferior da caixa de diálogo e insira o endereço de email da pessoa cujos dados você deseja acessar ou excluir.

1. Para enviar a solicitação, clique em **[!UICONTROL Criar]**.

   [!DNL Privacy Service] retorna uma ID de solicitação que você pode usar para verificar o status da sua solicitação.

### Solicitações de API {#api-requests}

Também é possível enviar solicitações de privacidade usando a API [!DNL Privacy Service]. Para referência de API geral, consulte a [documentação da API do Privacy Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service){target="_blank"}.

>[!PREREQUISITES]
>
>Obtenha as seguintes informações antes de enviar uma solicitação:
>
>* A ID da Organização IMS da sua organização (uma sequência de 24 caracteres alfanuméricos que termina em `@AdobeOrg`). Entre em contato com o Suporte da Adobe em `gdprsupport@adobe.com` se você não souber a ID da Organização IMS.
>* O endereço de email da pessoa cujos dados você deseja acessar ou excluir.

Use os seguintes valores de campo em sua solicitação:

| Campo | Valor |
|---|---|
| `companyContexts.namespace` | `imsOrgID` |
| `companyContexts.value` | Sua ID organizacional IMS |
| `users.action` | `access` ou `delete` |
| `users.userIDs.namespace` | `Email` |
| `include` | `marketo` para incluir dados de [!DNL Marketo Optimizer] e [!DNL Marketo Engage] |
| `regulation` | Exemplo: `ccpa` <br/>Alguns valores de regulamentos estão sendo alterados para incluir uma abreviação de estado (por exemplo, `ucpa_ut_usa`). Os valores mais antigos permanecem válidos por um período de transição. Consulte a [Visão geral das regras de privacidade](https://experienceleague.adobe.com/en/docs/experience-platform/privacy/regulations/overview){target="_blank"} para obter a lista atual antes de criar integrações com esses valores. |

O exemplo a seguir envia uma solicitação de exclusão de GDPR que inclui dados [!DNL Marketo Optimizer].

```json
{
  "companyContexts": [
    {
      "namespace": "imsOrgID",
      "value": "1231659F56A68A8B7F000101@AdobeOrg"
    }
  ],
  "users": [
    {
      "action": ["delete"],
      "userIDs": [
        {
          "namespace": "Email",
          "type": "standard",
          "value": "john.doe@adobe.com"
        }
      ]
    }
  ],
  "include": ["marketo"],
  "regulation": "gdpr"
}
```

[!DNL Privacy Service] retorna uma resposta semelhante à seguinte.

```json
{
  "requestId": "16331241037112570RX-245",
  "totalRecords": 1,
  "jobs": [
    {
      "jobId": "997b01e3-9568-402c-904b-b4e60a437875",
      "customer": {
        "user": {
          "action": ["delete"],
          "userIDs": [
            {
              "namespace": "Email",
              "value": "john.doe@adobe.com",
              "type": "standard",
              "namespaceId": 6,
              "isDeletedClientSide": false
            }
          ]
        }
      }
    }
  ]
}
```
