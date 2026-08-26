---
title: Metadados C2PA
description: Saiba como o Adobe Marketo Otimizer aplica automaticamente metadados C2PA a imagens geradas com IA gerativa e o que isso significa para o seu conteúdo.
feature: Assets, Content
role: User
source-git-commit: d1268dd4fadec58b5adedeaa295ca0624c2c2dcd
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 0%

---

# Metadados do C2PA

As organizações de marketing estão mais preocupadas do que nunca com a transparência do conteúdo, a divulgação de IA e a prevenção de adulteração de ativos. O Content Authenticity Initiative (CAI) na Adobe cria ferramentas compatíveis com o padrão técnico [Coalition for Content Provenance and Authenticity](https://c2pa.org/specifications/specifications/1.1/specs/C2PA_Specification.html#_trust_model) (C2PA). _Os metadados C2PA_ são informações criptografadas e invioláveis que podem ajudar os visualizadores a entender a linhagem do conteúdo e garantir a integridade dos ativos da marca. Essas informações incluem:

* Emissor ou signatário — Informações sobre a entidade ou empresa que emitiu a assinatura digital para certificar ou assinar o ativo.
* Data de emissão — A data em que os metadados do C2PA foram aplicados ao ativo.
* Crédito e uso — Informações sobre o produtor do ativo, incluindo nome, identificadores de mídia social ou outras informações relacionadas à identidade.
* Processo — Registros de qualquer edição ou modificação feita no ativo.
* Detalhes do dispositivo — Informações sobre o aplicativo ou dispositivo usado para criar ou editar o ativo.
* Ferramenta de IA usada — se a IA gerativa foi usada para criar o ativo, o nome do modelo usado pode ser incluído.
* Outras informações relevantes — dados adicionais também estão incluídos para ajudar a oferecer mais contexto sobre o histórico de um ativo.

Para obter informações abrangentes sobre o histórico de ativos, você pode usar a [ferramenta de inspeção](https://contentauthenticity.adobe.com/inspect) do Adobe Content Authenticity.

Os metadados C2PA persistem com o arquivo de imagem. Quando uma imagem gerada ou editada com IA gerativa é carregada para ou exportada do [!DNL Adobe Marketo Optimizer], seus metadados C2PA são preservados.

Para obter detalhes adicionais sobre a anexação automática de metadados C2PA nos aplicativos do Adobe CX Enterprise, consulte [_Generative AI content transparency_](https://experienceleague.adobe.com/pt-br/docs/cx-enterprise-ai/experience-cloud-ai/overview/content-transparency){target="_blank"} no AI no CX Enterprise guide.

>[!NOTE]
>
>Alguns métodos de importação de imagens para seu conteúdo, como extrair uma imagem de um PDF ou de uma fonte incorporada (base64), podem não preservar os metadados C2PA originais. Nesses casos, os metadados C2PA não podem ser lidos na origem e nenhum é criado para o resultado.

>[!BEGINSHADEBOX]

## Persistência de metadados C2PA por meio de canais {#channels}

Quando você inclui imagens em seu e-mail ou mensagens de WhatsApp, os metadados C2PA para as imagens entregues também são mantidos:

* **Email** - Quando você usar uma ação de jornada _Enviar email_, adicione a imagem ao seu conteúdo de email da biblioteca _Assets_. Quando o email é entregue, o recipient pode baixar a imagem da mensagem e os metadados do C2PA ficam intactos.
* **WhatsApp** - Adicione a imagem ao seu modelo de mensagem do WhatsApp na sua conta comercial do Meta. Você pode adicioná-lo diretamente do seu sistema ou baixar um arquivo de imagem da biblioteca do _Assets_. Use o modelo para uma ação de jornada _Enviar WhatsApp_. Quando a mensagem do WhatsApp é entregue, o recipient pode baixar a imagem da mensagem e os metadados do C2PA estão intactos.

>[!ENDSHADEBOX]

## Geração de imagem {#generate}

>[!INFO]
>
>Novas leis estão surgindo em torno da transparência generativa da IA, e a Adobe está trabalhando para atender aos requisitos aplicáveis em todas as jurisdições. Os metadados C2PA são a ferramenta de origem que o Adobe usa para atender aos requisitos dessas leis.

Quando você usa a IA gerativa para criar uma imagem para o seu conteúdo de email no [!DNL Marketo Optimizer], os metadados C2PA são anexados automaticamente à imagem gerada e nenhuma ação é necessária da sua parte. As ferramentas de IA gerativa produzem um elemento de metadados C2PA combinado para variantes de imagens com metadados existentes, incluindo a fonte original.

>[!NOTE]
>
>No momento, o [!DNL Marketo Optimizer] não oferece suporte a ações de edição manual de imagens. Os workflows de metadados C2PA para essas ações não são aplicáveis no momento.
