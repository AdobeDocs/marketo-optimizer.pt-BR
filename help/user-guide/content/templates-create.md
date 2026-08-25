---
title: Criar modelos de email
description: Saiba como criar modelos de email no Marketo Otimizer — crie um novo, salve um email de uma jornada como modelo ou converta uma imagem de design em um modelo de email.
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '873'
ht-degree: 1%

---


# Criar modelos de email

Você pode criar um modelo de email no [!DNL Adobe Marketo Optimizer] de três maneiras:

* **Criar um novo modelo** — Crie um modelo na biblioteca de modelos usando o espaço de design de email visual.
* **Salvar de um email de jornada** — Salve um email criado em uma jornada como um modelo reutilizável.
* **Converter uma imagem** — carregue uma imagem de design e use a IA gerativa para convertê-la em um modelo de email editável.

## Criar um novo modelo {#build-new}

1. Na navegação à esquerda, expanda **[!UICONTROL Gerenciamento de conteúdo]** e selecione **[!UICONTROL Modelos]**.
1. Clique em **[!UICONTROL Criar modelo]**.
1. Insira um **[!UICONTROL Nome do modelo]** e uma **[!UICONTROL Descrição]** opcional.
1. Defina o **[!UICONTROL Canal]** (tipo) para o modelo.

   >[!NOTE]
   >
   >Nesta versão do Beta, somente os modelos de email são compatíveis.

   <!-- 1. Optionally add **[!UICONTROL Tags]** to categorize the template. -->

1. Clique em **[!UICONTROL Criar]** para abrir o espaço de design de email.

1. Clique em **[!UICONTROL Editar corpo do email]** para acessar o espaço de design de conteúdo.

   Consulte [Criação de email](email-authoring.md) para obter informações detalhadas sobre o design de conteúdo.

1. Habilite opcionalmente a **[!UICONTROL Governança]** e configure o [bloqueio de conteúdo](template-content-governance.md) para restringir quais partes dos autores de modelo podem editar ao aplicar o modelo.

1. Clique em **[!UICONTROL Salvar]**.

## Salvar um email como modelo {#save-as-template}

Ao abrir o conteúdo de email que deseja reutilizar, salve-o diretamente na biblioteca de modelos na página de conteúdo de email.

1. Clique em **[!UICONTROL Modelo de conteúdo]** na parte superior da página.
1. Selecione **[!UICONTROL Salvar como modelo de conteúdo]**.
1. Insira um **[!UICONTROL Nome]** e uma **[!UICONTROL Descrição]** opcional.
1. Opcionalmente, adicione **[!UICONTROL Marcas]**.
1. Clique em **[!UICONTROL Criar]**.

O email original da jornada não é afetado. O modelo salvo está disponível na biblioteca de modelos para todos os usuários na sandbox. É possível atualizar o template criado para otimizar a reutilização:

* Editar texto e adicionar tokens de [personalização](email-authoring.md#personalize-content).
* Atualize ou substitua imagens e adicione links.
* Configurar [bloqueio de conteúdo](template-content-governance.md).

## Converter uma imagem em um modelo {#image-to-template}

O [!DNL Adobe Marketo Optimizer] pode converter uma imagem estática — como um modelo do Figma ou do Photoshop — em um modelo de email editável usando IA gerativa. Isso elimina a necessidade de recriar manualmente os layouts dos arquivos de design e é ideal para migrar designs de email existentes de outras plataformas. Esse recurso está disponível somente para modelos de conteúdo de email.

>[!BEGINSHADEBOX]

### Pré-requisitos

Antes de começar:

* Sua organização deve ter assinado o adendo da IA gerativa com a Adobe.
* Você deve ter a permissão **[!UICONTROL Gerar Conteúdo]** além de **[!UICONTROL Gerenciar modelos de conteúdo]**.
* O arquivo de imagem deve atender às seguintes especificações:
  * Formato: JPEG (.jpg, .jpeg) ou PNG (.png)
  * Tamanho máximo do arquivo: 10 MB
  * Largura recomendada: 600 a 800 pixels
  * Imagem clara e de alta qualidade com texto legível e elementos visuais distintos

>[!IMPORTANT]
>
>A imagem não deve conter informações de identificação pessoal (PII) ou dados confidenciais.

>[!ENDSHADEBOX]

### Criar o modelo

1. Na navegação à esquerda, expanda **[!UICONTROL Gerenciamento de conteúdo]** e selecione **[!UICONTROL Modelos]**.
1. Clique em **[!UICONTROL Criar modelo]**.
1. Insira um **[!UICONTROL Nome do modelo]** e uma **[!UICONTROL Descrição]** opcional.
1. Defina o **[!UICONTROL Canal]** como Email.

   <!--  Optionally add **[!UICONTROL Tags]** to categorize the template. -->

1. Clique em **[!UICONTROL Criar]**.

### Gerar o conteúdo do modelo

1. Na seção **[!UICONTROL Converter imagem em modelo]**:

   * Opcionalmente, selecione um **[!UICONTROL Tema da marca]** para aplicar as cores, fontes e espaçamento da sua marca na saída gerada.
   * Marque a caixa de seleção de confirmação para confirmar que a imagem não contém informações pessoalmente identificáveis (PII) ou outros dados confidenciais.
   * Clique em **[!UICONTROL Carregar imagem]** e selecione seu arquivo de imagem.

   >[!CAUTION]
   >
   >O upload de uma imagem exclui qualquer conteúdo atualmente no email e a substitui pelo modelo gerado.

1. Se solicitado, revise e aceite as Diretrizes do usuário da IA gerativa da Adobe.

1. Clique em **[!UICONTROL Abrir]** para iniciar o processo de conversão.

   A conversão normalmente é concluída em cerca de cinco minutos. Imagens complexas ou grandes podem levar até dez minutos. A conversão é executada em segundo plano — você pode sair e o modelo de rascunho é salvo automaticamente quando a conversão é concluída.

1. Atualize a página para ver o modelo concluído.

   >[!NOTE]
   >
   >O resultado não é exibido automaticamente. Atualize a página ou retorne à biblioteca de modelos para ver o modelo concluído.

1. Opcionalmente, use a seção **[!UICONTROL Feedback do conversor de imagem a modelo]** para compartilhar sugestões com a Adobe.

1. Clique em **[!UICONTROL Editar corpo do email]** para abrir o modelo convertido no espaço de design de email para edição.

1. Clique em **[!UICONTROL Salvar]**.

### Editar o conteúdo convertido

O conteúdo do modelo convertido é aberto no espaço de design como um modelo de email totalmente editável. Use as ferramentas padrão de design de conteúdo para:

* Editar texto e adicionar tokens de [personalização](email-authoring.md#personalize-content).
* Atualize ou substitua imagens e adicione links.
* Ajustar cores, fontes e espaçamento.
* Adicione, remova ou reorganize componentes de conteúdo.
* Habilitar governança e configurar [bloqueio de conteúdo](template-content-governance.md).

>[!IMPORTANT]
>
>A IA gerativa produz HTML estático com base na imagem visual. Revise todo o texto para obter a precisão e adicione personalização, conteúdo dinâmico e rastreamento manualmente após a conversão.

O modelo convertido é salvo automaticamente na biblioteca de modelos quando a conversão é concluída.

### Dicas para obter melhores resultados

Use as diretrizes a seguir para obter os melhores resultados da conversão de imagem em modelo:

**Antes da conversão:**

* Use a versão de resolução mais alta do arquivo de design.
* Projete em larguras de email padrão (600-800 pixels) e inclua o layout completo — cabeçalho por rodapé — em uma única imagem.
* Garanta contraste suficiente entre o texto e os planos de fundo e use tamanhos de fonte legíveis.

**Design para conversão precisa:**

* Use layouts simples e bem estruturados com uma separação clara entre as seções.
* Siga padrões padrão de email — cabeçalho, corpo, chamadas para ação, rodapé — em vez de designs complexos de várias camadas.
* Mantenha os elementos visuais distintos para que a IA possa identificar corretamente os limites estruturais.

**Após a conversão:**

* Teste a renderização em clientes de email e dispositivos antes de usar o modelo em uma jornada.
* Verificar alinhamento com cores da marca, fontes e diretrizes de estilo.
* Revise e aprimore a acessibilidade, incluindo o texto alternativo de imagem.
