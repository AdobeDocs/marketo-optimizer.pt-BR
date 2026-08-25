---
title: Configuração de canal de email
description: Crie e gerencie configurações de canal de email que vinculam a identidade do remetente, o subdomínio, o pool de IPs, o tipo de email e o rastreamento de URL do Marketo Otimizer.
feature: Administration
role: Admin
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 0%

---

# Configuração do canal de email

Uma configuração de canal é o objeto central que une a identidade do remetente, o subdomínio, o pool de IPs e as configurações de rastreamento. As ações de email no jornada fazem referência a uma configuração de canal para saber como enviar a mensagem. Antes de criar uma configuração, conclua a [delegação de subdomínio e a configuração do pool de IP](../start/email-deliverability.md).

* **Canal:** Email.
* **Tipo de email:** Marketing ou Transacional. Essa configuração determina se as regras de supressão se aplicam (Marketing as aplica; Transacional ignora a supressão de reclamação de spam por padrão para mensagens transacionais legítimas).
* **Parâmetros de cabeçalho:** Do nome, Do email, Nome para resposta, Email para resposta, Email para erro.
* **Subdomínio:** o subdomínio delegado usado para envio. O De email deve usar este subdomínio.
* **Pool de IPs:** o pool de IPs usado para entregar a mensagem.
* **Rastreamento de URL:** Habilite ou desabilite o rastreamento de cliques e aberturas; configure o domínio de rastreamento.
* **Marcas:** Marcas para organização e pesquisa.

## Criar uma configuração de canal de email {#create-email-channel-configuration}

>[!PREREQUISITES]
>
>* Pelo menos um [subdomínio](../start/email-deliverability.md#subdomain-delegation) deve ser delegado e estar Ativo.
>* Pelo menos um [pool de IPs](../start/email-deliverability.md#ip-pools) deve ser atribuído à sua organização.
>* Você precisa ter a função Administrador.
>* Revise as [limitações atuais](../start/email-deliverability.md#limitations) — os pools de IP dedicados não estão disponíveis na Beta.

1. Na navegação à esquerda [!DNL Adobe Marketo Optimizer], expanda **[!UICONTROL Administração]** e selecione **[!UICONTROL Canais]**.
1. No painel, expanda **[!UICONTROL Configurações de email]** e selecione **[!UICONTROL Configurações de canal]**.
1. Clique em **[!UICONTROL Criar configuração de canal]**.
1. Insira um Nome (por exemplo, _Contoso B2B Marketing — América do Norte_) e uma Descrição opcional.
1. Selecione o canal de **[!UICONTROL Email]**.
1. (Opcional) Selecione tags para categorizar a configuração.
1. Na seção **[!UICONTROL Tipo de email]**, escolha Marketing ou Transacional.
1. Na seção **[!UICONTROL Subdomínio]**, selecione um subdomínio delegado anteriormente.
1. Na seção **[!UICONTROL Pool de IPs]**, selecione um pool de IPs Ativo.

   Na Beta, somente o pool de IPs compartilhados está disponível. Você pode passar o mouse sobre os IPs para visualizar registros PTR.

1. Configure os **[!UICONTROL Parâmetros de cabeçalho]**:
   * Do Nome (por exemplo, &quot;Marketing da Contoso&quot;).
   * Do Email — deve usar o subdomínio selecionado (por exemplo, `marketing@mail.contoso.com`).
   * Nome para Resposta e Email para Resposta — o padrão é _De_ se estiver em branco.
   * E-mail de erro — endereço que recebe notificações de falha na entrega.
1. Habilite **[!UICONTROL Rastreamento de URL]** e selecione o domínio de rastreamento.
1. Clique em **[!UICONTROL Enviar]**.

>[!NOTE]
>
>Após o envio, o sistema executa a validação: status do subdomínio, registro MX, alinhamento SPF/DKIM/DMARC, preparação do pool de IP, registro FBL. A configuração passa por Rascunho → Processamento → Ativo.

>[!NOTE]
>
>Se a validação falhar, a configuração será movida para o status **[!UICONTROL Falha]**. Abra a configuração para exibir o motivo da falha — as causas comuns são falha de validação de registro MX, IPs no pool que não correspondem à configuração ou desalinhamento da DMARC. Resolver e enviar novamente.

## Edição ou exclusão de uma configuração de canal {#edit-channel-configuration}

Você pode editar as configurações de canal após a criação, mas com uma restrição importante: **O canal não pode ser alterado.** Uma configuração está associada ao seu canal.

Quando você edita uma configuração que está em uso:

* **Para jornadas publicadas:** a alteração é aplicada na próxima recorrência ou execução. As execuções em andamento continuam com as configurações anteriores.
* **Para mensagens transacionais ou em tempo real:** as alterações se propagam dentro de aproximadamente cinco minutos.

>[!WARNING]
>
>A exclusão de uma configuração de canal é permanente. Não é possível excluir uma configuração à qual uma jornada ativa faz referência. Remova ou reatribua todas as ações de email primeiro.

Para excluir uma configuração, primeiro remova ou atualize cada ação de email que a referencie em [Adicionar emails ao jornada](../marketing/email-channel.md#define-email-properties). [!DNL Marketo Optimizer] não exclui uma configuração que está sendo usada por uma jornada ativa.

## Configurações de vários canais {#multiple-channel-configurations}

A maioria das organizações B2B usa configurações de vários canais para separar marcas, regiões ou tipos de envio. Padrões comuns:

* Uma configuração de marketing separada por unidade de negócios (por exemplo, *Marketing BU-A*, *Marketing BU-B*).
* Uma configuração transacional dedicada com Tipo de email = Transacional para notificações de produto ou contrato.
* Configurações específicas de região usando subdomínios específicos de região (por exemplo, `mail.eu.contoso.com`, `mail.us.contoso.com`) para alinhar com ISPs regionais e conformidade.

>[!TIP]
>
>Nomeie suas configurações com uma convenção clara e estruturada — por exemplo: *[Marca] - [Região] - [Tipo]*. Isso se torna crítico quando você tem uma dúzia ou mais de configurações.
