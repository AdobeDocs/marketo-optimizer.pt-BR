---
title: Modo escuro para conteúdo de email
description: Saiba mais sobre o design de email no modo escuro no Marketo Otimizer. Visualize a renderização, personalize as configurações e teste em clientes de email.
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '1476'
ht-degree: 7%

---

# Modo escuro para conteúdo de email {#dark-mode}

>[!CONTEXTUALHELP]
>id="ajo-b2b_dark_mode"
>title="Alternar para o modo escuro"
>abstract="Alterne para o modo escuro para visualizar a renderização e definir configurações personalizadas. <br>A renderização final depende do cliente de email do destinatário. Nem todos os clientes de email permitem o modo escuro."

>[!CONTEXTUALHELP]
>id="ajo-b2b_dark_mode_preview"
>title="Alternar para o modo escuro"
>abstract="Alterne para o modo escuro para visualizar a renderização em clientes de email compatíveis. <br>A renderização final depende do cliente de email do destinatário. Observe que nem todos os clientes de email oferecem suporte ao modo escuro."

_Modo escuro_ permite que um cliente ou aplicativo de email de suporte exiba emails com planos de fundo mais escuros e cores mais claras para texto, botões e outros elementos visuais. Esse tipo de monitor pode reduzir a tensão ocular, economizar bateria e melhorar a legibilidade em ambientes com pouca luminosidade, proporcionando uma experiência de visualização mais confortável. Como uma tendência crescente nos principais sistemas operacionais e aplicativos, agora é uma consideração importante no design de email moderno para garantir que o conteúdo permaneça legível e visualmente atraente para todos os usuários.

À medida que você [cria seu conteúdo de email](./email-authoring.md) no espaço de design visual do [!DNL Marketo Optimizer], é possível alternar para o modo de exibição _**[!UICONTROL Escuro]**_. Nesta visualização, também é possível definir configurações personalizadas específicas para oferecer suporte a clientes de email quando o modo escuro estiver ativado.

## Considerações do cliente de email {#email-client-considerations}

Há uma variação significativa na maneira como diferentes clientes de email e aplicativos aplicam o modo escuro. Por isso, considere com cuidado as expectativas de renderização no modo escuro. Antes de usar o modo escuro no espaço de design de email, considere os seguintes casos de uso de cliente de email:

+++Clientes que não oferecem suporte ao modo escuro

Alguns clientes de email não oferecem suporte a esse recurso, como:

* [!DNL Yahoo! Mail]
* [!DNL AOL]

Se você definir configurações personalizadas de modo escuro no design de email, esses clientes de email não poderão exibir nenhuma renderização de modo escuro.

+++

+++Clientes que aplicam seu próprio modo escuro

Alguns clientes de email aplicam sistematicamente seu próprio modo escuro padrão a todos os emails recebidos. Eles ajustam automaticamente cores, planos de fundo, imagens e outros elementos de acordo com suas configurações de modo escuro e as configurações externas não são possíveis. Esses clientes incluem:

* Gmail (Webmail Para Desktop, iOS, Android™, Webmail Para Dispositivos Móveis)
* Outlook Windows
* Outlook Windows Mail

Nesse caso, as configurações do modo escuro do cliente substituem as configurações personalizadas do modo escuro definidas no [!DNL Marketo Optimizer].

+++

+++Clientes que oferecem suporte ao modo escuro personalizado

Muitos dos clientes de email mais populares oferecem suporte à renderização personalizada no modo escuro com a consulta `@media (prefers-color-scheme: dark)`, que é o método usado pelos estilos de email [!DNL Marketo Optimizer]. Esta lista de clientes inclui:

* Apple Mail macOS
* Apple Mail iOS
* Outlook macOS
* Outlook.com
* Outlook iOS
* Outlook Android™

Nesse caso, as configurações específicas que você define em [!DNL Marketo Optimizer] são renderizadas. No entanto, algumas restrições podem ser aplicadas de acordo com cada cliente de email. Por exemplo, alguns clientes (como o Apple Mail 16 (macOS 13)) não geram o modo escuro se as imagens estiverem presentes no conteúdo de email.

Para obter os melhores resultados, teste seu conteúdo com os clientes de email que você está direcionando.

+++

## Design para modo escuro

O espaço de design visual do [!DNL Marketo Optimizer] fornece dois tipos de ferramentas para estilizar o conteúdo de email no modo escuro:

* Use a [função de visualização](#preview-dark-mode) para revisar a renderização padrão do modo escuro para a maioria dos clientes de email de suporte.

* Se quiser substituir as configurações padrão de clientes de email de suporte, defina e aplique as [configurações personalizadas do modo escuro](#custom-dark-mode) ao seu conteúdo de email.

### Visualizar modo escuro padrão {#preview-dark-mode}

1. Abra o conteúdo do email no espaço de design de email.

   Na parte superior direita da tela de desenho, há um seletor de claro-escuro que alterna a exibição do conteúdo entre o modo claro (padrão) e escuro.

   ![Tela de design de email mostrando o seletor de modo de luz no canto superior direito](assets/email-color-mode-light-selector.png){width="700" zoomable="yes"}

1. Altere o seletor para _Modo escuro_ ( ![Ícone de modo escuro](../assets/do-not-localize/icon-content-dark-mode.svg) ).

   A tela de desenho exibe o conteúdo usando a pré-visualização padrão do modo escuro.

   Por padrão, a visualização do modo escuro aplica o esquema de cores `full color invert` a todos os elementos, exceto imagens e ícones. Esse esquema de cores detecta áreas com elementos claros e escuros e os inverte. Os planos de fundo claros se tornam escuros e o texto escuro se torna claro, ou os planos de fundo escuros se tornam claros e o texto claro se torna escuro.

   ![Tela de design de email mostrando o seletor de modo escuro e o conteúdo de email exibidos no modo escuro](assets/email-color-mode-dark-selector.png){width="700" zoomable="yes"}

>[!CAUTION]
>
>A renderização final pode variar de acordo com o cliente de email do recipient. Para ver uma simulação que se aproxime o máximo possível do resultado final de cada cliente de email, use a integração de renderização de email do Litmus disponível por meio de **[!UICONTROL Simular conteúdo]** no espaço de design de email.

### Definir as configurações personalizadas do modo escuro {#custom-dark-mode}

>[!CONTEXTUALHELP]
>id="ajo-b2b_dark_mode_image"
>title="Usar uma imagem específica para o modo escuro"
>abstract="Selecione outra imagem para o modo escuro. <br>Adicionar uma imagem específica não garante que ela seja renderizada corretamente em todos os clientes de email. Nem todos os clientes de email permitem o modo escuro."

Depois de alternar para o modo escuro, você pode editar elementos de estilo específicos do seu conteúdo, que são exibidos somente quando o modo escuro está ativado no cliente de email do recipient (desde que seja compatível com esse recurso).

>[!NOTE]
>
>A renderização final no modo escuro depende de cada cliente de email, portanto, os resultados podem variar de um para o outro. Revise as [considerações sobre o cliente de email](#email-client-considerations) para obter mais informações.

O estilo de modo escuro personalizado usa a consulta CSS `@media (prefers-color-scheme: dark)` para detectar se o cliente de email está definido para o modo escuro e aplicar o design de tema escuro definido.

_Para definir configurações personalizadas do modo escuro :_

1. Se necessário, mova o seletor para _Modo escuro_ ( ![Ícone de modo escuro](../assets/do-not-localize/icon-content-dark-mode.svg) ) na parte superior direita da tela de design.

1. Edite quaisquer atributos de cor de estilo, como texto, planos de fundo ou botões.

![Painel de configurações de estilo de texto no modo escuro mostrando opções de cor e fonte](assets/email-color-mode-dark-text-settings.png){width="700" zoomable="yes"}

1. Para imagens e ícones, defina ativos específicos somente para o modo escuro.

   Não é possível alterar as cores das imagens e dos ícones, mas você pode definir ativos alternativos a serem usados no modo escuro. Você pode experimentar diferentes combinações de cores para seus ícones ou fazer ajustes de cores e saturação para imagens fotográficas.

   ![Ícones com combinações de cores diferentes](../assets/do-not-localize/color-contrast-images-diagram.svg){width="80%"}

   Selecione qualquer imagem e alterne para o **[!UICONTROL modo escuro]** usando a opção dedicada no painel **[!UICONTROL Configurações]**. Em seguida, selecione um ativo de imagem diferente do seletor de ativos do Marketo Design Studio.

   Consulte [Inserir uma imagem do Marketo Design Studio](./email-authoring.md#insert-image) para obter mais informações sobre como selecionar um ativo de imagem.

1. A qualquer momento durante as alterações de design, selecione **[!UICONTROL Alternar para o modo de exibição dinâmico]** para verificar como o conteúdo pode ser renderizado em vários tamanhos de dispositivo.

   Nesta exibição, altere o seletor para _Modo escuro_ ( ![Ícone de modo escuro](../assets/do-not-localize/icon-content-dark-mode.svg) ) para visualizar a versão de modo escuro do seu conteúdo em diferentes dispositivos.

   ![Painel de exibição em tempo real mostrando o conteúdo de email no modo escuro em diferentes tamanhos de dispositivo](assets/email-color-mode-dark-live-view.png){width="800" zoomable="yes"}

   >[!CAUTION]
   >
   >A visualização em tempo real é uma visualização genérica criada para comparar a aparência da renderização em vários tamanhos de dispositivo. A renderização final pode variar dependendo do cliente de email do recipient.

1. Quando as alterações no modo escuro estiverem concluídas, clique em **[!UICONTROL Simular Conteúdo]** para usar os revisores de texto e as ferramentas de revisão para testar o design do email.

1. Se você tiver uma conta do Litmus Enterprise, selecione **[!UICONTROL Renderizar email]** para ver a renderização final no modo escuro para vários clientes de email na integração do Litmus.

   >[!CAUTION]
   >
   >Embora a simulação se aproxime da forma como os emails aparecem no modo escuro, a renderização real pode ser diferente devido a variações nos provedores de serviços de email ou nas configurações no nível do dispositivo.

## Práticas recomendadas {#best-practices}

À medida que a adoção do modo escuro aumenta nos principais clientes de email, é essencial considerar como seus emails são renderizados em ambientes claros e escuros, esteja você usando o [modo escuro personalizado](#custom-dark-mode) ou não.

O modo escuro pode alterar cores, planos de fundo e imagens — às vezes substituindo as opções de design. Para garantir a consistência visual, a acessibilidade e a integridade da marca, siga estas práticas recomendadas:

| Prática |            |
| -------- | ---------- |
| Otimize suas imagens e logotipos | Lista de verificação:<ul><li>Salve logotipos e ícones como arquivos PNG com fundo transparente para evitar caixas brancas visíveis no modo escuro. <li>Evite imagens com fundos brancos ou claros codificados. <li>Se a transparência não for uma opção, coloque as imagens em um plano de fundo sólido no design para evitar inversões de cores estranhas. |
| Veja seus planos de fundo | Lista de verificação:<ul><li>Verifique se há contraste suficiente entre o texto e as cores do plano de fundo para facilitar a leitura nos modos claro e escuro. <li>Evite depender apenas das cores do plano de fundo para o conteúdo crítico. Alguns clientes substituem as cores do plano de fundo no modo escuro, portanto, verifique se as informações principais ainda estão visíveis. |
| Criar conteúdo acessível no modo escuro | Lista de verificação:<ul><li>Use combinações de cores fáceis de distinguir para pessoas com daltonismo. <li>Use uma paleta de tons médios para garantir o contraste em planos de fundo claros e escuros. <li>Use combinações de cores acessíveis com alto contraste para melhorar a legibilidade e atender aos padrões do [!DNL Web Content Accessibility Guidelines (WCAG)]. Use ferramentas como o [!DNL WebAIM Contrast Checker] para verificar o contraste de cores. <li>Evite fontes finas, pois elas podem afetar a legibilidade. Se sua marca requer uma fonte fina, coloque-a em negrito no modo escuro. <li>Ignorar branco puro em preto puro, o que pode causar tensão ocular e pode ser invertido automaticamente em alguns clientes de email. <li>Fornecer estilo de fallback acessível se o modo escuro não for compatível. |
| Testar seus emails em um ambiente no modo escuro | Lista de verificação:<ul><li>Use a [visualização de modo escuro](#preview-dark-mode) no espaço de design de email, que usa esquemas de cores invertidas para detectar problemas antecipadamente. <li>Se você tiver uma conta Litmus Enterprise, use a opção **[!UICONTROL Renderizar email]** para simular seus designs nos principais clientes de email (como Apple Mail, Gmail e Outlook) e ver como as cores e as imagens se comportam no modo escuro. |

