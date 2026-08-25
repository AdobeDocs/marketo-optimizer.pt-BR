---
title: Regras de negócios
description: Crie e gerencie conjuntos de regras para aplicar regras de limite de frequência e horas de silêncio que controlam com que frequência e quando os clientes recebem mensagens de marketing.
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '2965'
ht-degree: 10%

---

# Regras de negócios {#business-rules}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_business_rules_rule_sets"
>title="Conjuntos de regras"
>abstract="Use conjuntos de regras para aplicar as regras de limite de frequência ou horário de silêncio aos diferentes tipos de comunicações de marketing. Você também pode criar conjuntos de regras para excluir jornadas para parte do público-alvo com base em regras de limite de frequência."

As regras de negócios permitem que sua organização defina e agrupe várias regras em conjuntos de regras para que os profissionais de marketing possam aplicá-las aos emails, conforme necessário. Isso oferece maior granularidade para limitar a frequência e a quantidade de jornadas que um cliente pode inserir em um determinado período de tempo ou controlar a frequência com que os usuários recebem mensagens, dependendo do tipo de comunicação.

Você pode criar dois tipos de conjuntos de regras:

* Os conjuntos de regras do **Canal** aplicam regras aos canais de comunicação. Eles permitem definir:

  * **Regras de limite de frequência** - Exemplo: *Não enviar mais de uma comunicação por email, SMS, Push, Correspondência direta ou WhatsApp por dia.*
  * **Regras de horário de silêncio** - Exemplo: *Não enviar mensagens de email fora do horário das 8h00 às 9h00.*

* Os conjuntos de regras **Jornada** aplicam regras de limite de simultaneidade e de entrada a uma jornada. (Ainda não suportado para a versão do Beta.)

>[!PREREQUISITES]
>
>Para trabalhar com regras de negócios, você precisa das seguintes permissões do CX Enterprise:
>
>* **[!UICONTROL Exibir Regras de Frequência]**: acessar e exibir regras de negócios.
>* **[!UICONTROL Gerenciar Regras de Frequência]**: Criar, editar ou excluir regras de negócios.

## Acessar e gerenciar conjuntos de regras {#access-manage}

Para acessar todos os conjuntos de regras existentes, expanda **[!UICONTROL Administração]** na navegação à esquerda e selecione **[!UICONTROL Regras de negócio]**.

![página da lista de Regras de Negócios](./assets/business-rules-list.png){width="800" zoomable="yes"}

### Conjuntos de regras globais e personalizadas {#global-custom}

Ao acessar _Conjuntos de Regras_ pela primeira vez, um conjunto de regras padrão é pré-criado e está ativo: **_[!UICONTROL CONJUNTO DE REGRAS GLOBAL]_**. Esse é um conjunto de regras global que pode ser aplicado para controlar a frequência com que os usuários recebem mensagens em um ou vários canais. As regras definidas neste conjunto de regras se aplicam a todos os canais selecionados.

![CONJUNTO DE REGRAS GLOBAL criado e ativo por padrão](./assets/business-rules-list-global-default.png){width="700" zoomable="yes"}

Além desse conjunto de regras padrão, você pode criar seus próprios conjuntos de regras personalizados e aplicá-los a uma jornada ou nó de canal para usar regras específicas de limite e período de silêncio.

### Abrir um conjunto de regras {#open-rule-set}

Clique no nome de um conjunto de regras para exibir e editar suas definições de regras. Todas as regras incluídas nesse conjunto de regras são listadas. Use o _Mais menu_ ( **...** ) na parte superior direita para ativá-lo, desativá-lo ou excluí-lo.

![Use o menu Mais para ativar ou desativar o conjunto de regras](./assets/business-rules-activate-rule-set.png){width="700" zoomable="yes"}

### Editar as regras {#edit-rules}

Para qualquer regra de rascunho no conjunto de regras, clique no ícone _Editar_ ( ![Editar ícone](../assets/do-not-localize/icon-edit.svg) ) ao lado do nome da regra para editar as configurações da regra. Você também pode clicar no ícone _Mais menu_ ( **...** ) para ativar ou excluir a regra.

![Regra definir regra de lista Mais opções de menu](./assets/business-rules-activate-rule.png){width="500" zoomable="yes"}

Para desativar uma regra, clique no ícone _Desativar_ ( ![Ícone Desativar](../assets/do-not-localize/icon-deactivate.svg) ) ao lado da regra ativa. No diálogo de confirmação, clique em **[!UICONTROL Desativar]**. O status muda para **_[!UICONTROL Inativo]_** e a regra não se aplica a futuras execuções de mensagem. As mensagens em execução no momento não são afetadas.

>[!NOTE]
>
>A desativação de uma regra ou conjunto de regras não afeta ou redefine qualquer contagem em perfis individuais.

## Criar e ativar conjuntos de regras personalizados {#create}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_rule_set_domain"
>title="Domínio do conjunto de regras"
>abstract="Ao criar um conjunto de regras, é necessário determinar se as regras no conjunto aplicarão regras de limitação específicas para canais de comunicação ou jornadas."

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_rule_sets_category"
>title="Selecionar a categoria da regra da mensagem"
>abstract="Quando ativadas e aplicadas a uma mensagem, todas as regras de frequência correspondentes à categoria selecionada serão automaticamente aplicadas a essa mensagem. Atualmente, somente a categoria Marketing está disponível."

>[!CONTEXTUALHELP]
>id="ajob2b-prime_rule_type"
>title="Tipo de regra"
>abstract="Selecione o tipo de regra desejado para o conjunto de regras de canal: use o tipo **Limite de frequência** para aplicar regras de limite aos canais de comunicação. Por exemplo, não envie mais de uma comunicação por email ou SMS por dia. Selecione **Horário de silêncio** para definir exclusões com base no tempo para garantir que nenhuma mensagem seja enviada durante horários específicos."

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_rule_sets_duration"
>title="Redefinir frequência de limite"
>abstract="Selecione o período de calendário usado para redefinir o contador de limite: por hora, dia, semana ou mês. O contador é automaticamente redefinido para 0 no início de cada novo período."

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_rule_set_rule_capping"
>title="Limite de regras"
>abstract="Definir a limitação para a regra. Dependendo do domínio do conjunto de regras e da seleção no campo “Tipo de regra”, este campo pode definir o número máximo de mensagens que podem ser enviadas a um perfil ou o número máximo de jornadas das quais o perfil pode participar ou nas quais pode ser inscrito simultaneamente."

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_journey_business_rules"
>title="Conjunto de regras"
>abstract="Selecione o conjunto de regras a ser aplicado à ação personalizada."

>[!NOTE]
>
>É possível criar até 10 conjuntos de regras para o domínio do canal e 10 conjuntos de regras para o domínio do jornada, para um total de 20 conjuntos de regras.

1. Expanda **[!UICONTROL Administração]** na navegação à esquerda e selecione **[!UICONTROL Regras de negócio]**.

1. Na página da lista _[!UICONTROL Conjuntos de regras]_, clique em **[!UICONTROL Criar conjunto de regras]** na parte superior direita.

   ![Caixa de diálogo Criar Conjunto de Regras](./assets/business-rules-create-rule-set-dialog.png){width="400"}

1. Insira um **[!UICONTROL Nome]** exclusivo (obrigatório) para o conjunto de regras e adicione uma **[!UICONTROL Descrição]** (opcional).

1. Selecione o conjunto de regras **[!UICONTROL Domínio]**.

   * **[!UICONTROL Canal]** - Aplique regras de limitação ou regras de horários de silêncio aos canais de comunicação.
   * **[!UICONTROL Jornada]** - Aplique regras de limite de entrada e simultaneidade a uma jornada.

   >[!IMPORTANT]
   >
   >As regras de Jornada ainda não são compatíveis com esta versão do Beta.

1. Clique em **[!UICONTROL Salvar]**.

   ![Novo conjunto de regras](./assets/business-rules-new-rule-set.png){width="700" zoomable="yes"}

### Adicionar as regras {#add-rules}

Depois de criar o conjunto de regras, adicione cada regra que deseja incluir.

1. Clique em **[!UICONTROL Adicionar regra]**.

1. Configure os parâmetros da regra de acordo com sua finalidade.

   Os parâmetros disponíveis para a regra dependem do domínio do conjunto de regras selecionado em sua criação.

   ![Parâmetros de regra definidos para uma regra de limite de entrada de jornada](./assets/business-rules-journey-entry-cap.png){width="700" zoomable="yes"}

   Informações detalhadas sobre como configurar o jornada e as regras de canal estão disponíveis nestas seções:

   <!-- * [Journey capping](../conflict-prioritization/journey-capping.md) -->
   * [Limite de frequência por canal e tipo de comunicação](#frequency-capping)
   * [Horário de silêncio](#quiet-hours)

1. Clique em **[!UICONTROL Criar regra]** para confirmar a criação da regra.

   A nova regra está listada no conjunto de regras com o status _Rascunho_.

1. Repita as etapas anteriores para adicionar quantas regras forem necessárias para o conjunto de regras.

   Quando criada, uma regra tem o status _[!UICONTROL Rascunho]_ e ainda não pode afetar nenhuma mensagem.

   ![Regras de rascunho em um conjunto de regras](./assets/rule-set-draft-rules.png){width="700" zoomable="yes"}

1. Para ativar uma regra para o conjunto de regras, clique no ícone do menu _Mais_ ( **...** ) ao lado do nome da regra e escolha **[!UICONTROL Ativar]**.

   No diálogo de confirmação, clique em **[!UICONTROL Ativar]**.

### Ativar o conjunto de regras {#activate-rule-set}

Ativar o conjunto de regras o disponibiliza para aplicar a uma jornada ou mensagem de canal. Quando um conjunto de regras está ativo, não é possível adicionar mais regras a ele. Você pode desativá-la para fazer alterações e depois ativá-la novamente.

1. Abra o conjunto de regras na página de lista _Conjuntos de Regras_.

1. Clique no _Mais menu_ ( **...** ) na parte superior direita e escolha **[!UICONTROL Ativar Conjunto de Regras]**.

   ![Clique no menu Mais para acessar a ação de ativação](./assets/business-rules-activate-rule-set.png){width="700" zoomable="yes"}

1. No diálogo de confirmação, clique em **[!UICONTROL Ativar]**.

   >[!NOTE]
   >
   >Pode levar até 10 minutos para que uma regra ou um conjunto de regras seja totalmente ativado. Não é necessário modificar mensagens ou republicar jornadas para que uma regra entre em vigor.

É possível aplicar o conjunto de regras ativo a uma mensagem ou jornada, dependendo da configuração de domínio do conjunto de regras.

## Limite de frequência por canal {#frequency-capping}

Defina limites de frequência por canal e tipo de comunicação para limitar quantas mensagens um perfil recebe e evitar sobrecarregar os clientes com comunicações semelhantes. Os conjuntos de regras de canal aplicam regras de limitação aos canais de comunicação. Por exemplo, não envie mais de uma comunicação por email ou SMS por dia.

O uso de conjuntos de regras de canal permite definir o limite de frequência por tipo de comunicação para evitar sobrecarga de clientes com mensagens semelhantes. Por exemplo, você pode criar um conjunto de regras para limitar o número de _comunicações promocionais_ enviadas aos seus clientes e outro conjunto de regras para limitar o número de _boletins informativos_ enviados a eles. Em seguida, você pode optar por aplicar a comunicação promocional ou o conjunto de regras de boletins informativos.

>[!IMPORTANT]
>
>Para garantir que o limite do nível de canal funcione corretamente, escolha o namespace de prioridade mais alta ao criar uma jornada. Saiba mais sobre a prioridade de namespace no [Guia do serviço de identidade da Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/identity/features/identity-graph-linking-rules/namespace-priority){target="_blank"}

### Criar uma regra de limitação de canal {#create-capping-rule}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_rule_sets_channel"
>title="Definir os canais aos quais a regra se aplica"
>abstract="Selecione pelo menos um canal. O limite se aplica em canais como uma contagem total."

1. Selecione o conjunto de regras de canal ao qual deseja adicionar a regra de limitação ou crie um novo conjunto de regras de canal.

1. Na página do conjunto de regras, clique em **[!UICONTROL Adicionar regra]** e digite um nome exclusivo para a regra.

   >[!NOTE]
   >
   > O campo _[!UICONTROL Categoria]_ especifica a categoria de mensagens para a regra. Atualmente, este campo é somente leitura e somente a categoria **[!UICONTROL Marketing]** está disponível.

1. Para o _[!UICONTROL Tipo de Regra]_, escolha **[!UICONTROL Limite de canal]**.

   ![Limite de canal selecionado como o tipo de regra](./assets/business-rules-frequency-capping-rule-type.png){width="700" zoomable="yes"}

1. No campo **[!UICONTROL Contagem de limites]**, defina o valor de limite para sua regra.

   Esse valor é o número máximo de mensagens que podem ser enviadas para um perfil de usuário individual a cada mês, semana, dia ou hora, de acordo com sua seleção nos outros campos.

1. Para **[!UICONTROL Redefinir a frequência de limite]**, selecione se deseja que o limite seja aplicado.

   O limite de frequência se baseia no período de calendário selecionado. Ela é redefinida no início do intervalo de tempo correspondente. Escolha a expiração do contador para cada período:

   * **[!UICONTROL Por hora]** - O limite de frequência é válido para o número de horas selecionado. O contador é redefinido automaticamente no início de cada janela de tempo. Para um limite de frequência de 1 hora, ele é redefinido a cada hora, coincidindo com o final de uma hora UTC.
   * **[!UICONTROL Diariamente]** - O limite de frequência diária é válido para o dia até 23:59:59 UTC e é redefinido para 0 no início do dia seguinte.
   * **[!UICONTROL Semanalmente]** - O limite de frequência é válido até sábado, 23:59:59 UTC dessa semana. A data de expiração se aplica independentemente de quando a regra foi criada. Por exemplo, se a regra for criada na quinta-feira, ela será válida até o sábado às 23:59:59.
   * **[!UICONTROL Mensal]** - O limite de frequência é válido até o último dia do mês às 23:59:59 UTC. Por exemplo, a expiração mensal de janeiro é 01-31 23:59:59 UTC.

   >[!IMPORTANT]
   >
   >* Para garantir a precisão, escolha o namespace de prioridade mais alta ao criar uma jornada. Saiba mais sobre a prioridade de namespace no [guia do serviço de identidade da plataforma](https://experienceleague.adobe.com/pt-br/docs/experience-platform/identity/features/identity-graph-linking-rules/namespace-priority){target="_blank"}<br/>
   >
   >* O valor do contador de perfil é atualizado quando a comunicação é entregue. Considere isso ao enviar grandes volumes de comunicações, pois a taxa de transferência pode fazer com que o recipient receba o email em minutos ou até horas após o início da comunicação (caso você esteja enviando milhões de comunicações simultaneamente). Isso é importante no caso de um recipient receber duas comunicações próximas. Recomenda-se que você separe as comunicações por pelo menos duas horas, quando possível, para fornecer tempo suficiente para que o recipient receba a comunicação e o valor do contador seja atualizado adequadamente.

1. Use o campo **[!UICONTROL A cada]** para definir a frequência da regra de limitação em várias horas, dias, semanas ou meses (dependendo do período especificado).

   Insira um valor que corresponda ao tipo de duração selecionado: 1-23 para _Por Hora_, 1-30 para _Diariamente_, 1-4 para _Semanalmente_ e 1-3 para _Mensalmente_.

   O contador é automaticamente redefinido para 0 quando uma nova janela de tempo é iniciada. Para um limite de frequência de dois dias, essa redefinição ocorre a cada dois dias à meia-noite UTC.

1. Selecione os canais que deseja usar para esta regra:

   * **[!UICONTROL Email]**
   * **[!UICONTROL SMS]** (atualmente não há suporte para esta versão do Beta)
   * **[!UICONTROL Notificação por push]** (não há suporte no momento para esta versão do Beta)
   * **[!UICONTROL Correspondência direta]** (atualmente não há suporte para esta versão do Beta)
   * **[!UICONTROL WhatsApp]** (não suportado no momento nesta versão do Beta)

   ![Canais selecionados para a regra de limite de frequência](./assets/business-rules-channel-capping.png){width="700" zoomable="yes"}

   Selecione vários canais se desejar aplicar o limite em todos os canais selecionados como uma contagem total.

   Por exemplo, defina o limite como 5 e selecione os canais de Email e SMS. Se um perfil já tiver recebido três emails de marketing e duas mensagens SMS de marketing para o período selecionado, esse perfil será excluído do próximo delivery de qualquer email de marketing ou mensagem SMS.

1. Clique em **[!UICONTROL Salvar]** para confirmar a criação da regra.

   Sua regra de frequência é adicionada ao conjunto de regras com o status _[!UICONTROL Rascunho]_.

1. Repita as etapas acima para adicionar quantas regras forem necessárias ao conjunto de regras.

1. Quando a regra de limitação estiver pronta para ser aplicada a mensagens, ative a regra e o conjunto de regras.

### Aplicar o conjunto de regras de limite de canal {#apply-capping-rule}

1. Ao criar uma jornada, adicione um dos [nós de ação](../marketing/action-nodes.md) de Envio para um canal que você selecionou para a regra e edite o conteúdo da mensagem.

1. Na guia _[!UICONTROL Ações]_, defina a opção **[!UICONTROL Regras de negócio]** para o conjunto de regras com a regra de limite de frequência.

   ![Opção de regras de negócios definida para o conjunto de regras de limite de frequência na guia Ações](./assets/business-rules-frequency-capping-email-actions.png){width="600" zoomable="yes"}

   >[!NOTE]
   >
   >Somente conjuntos de regras ativados estão disponíveis na lista.

   <!--Messages where the category selected is **[!UICONTROL Transactional]** will not be evaluated against business rules.-->

1. Antes de ativar a jornada, agende a execução dela pelo menos 10 minutos no futuro.

   Isso fornece o tempo necessário para preencher os valores do contador no perfil da regra de negócios selecionada. Se você ativar a jornada imediatamente, os valores do contador do conjunto de regras não poderão ser preenchidos nos perfis dos destinatários e a mensagem não será contada como suas regras de limite de frequência para os conjuntos de regras personalizados.

<!-- 
1. You can view the number of profiles excluded from delivery in the [Customer Journey Analytics report](../reports/report-gs-cja.md), and in the [Live report](../reports/live-report.md), where frequency rules will be listed as a possible reason for users excluded from delivery.

-->

>[!NOTE]
>
>Várias regras podem ser aplicadas ao mesmo canal, mas quando o limite inferior for atingido, o perfil será excluído dos próximos deliveries.

Ao testar as regras de frequência, é recomendável usar um perfil de teste recém-criado, pois quando um limite de frequência de perfil é atingido, não há como redefinir o contador até o próximo período. A desativação de uma regra permite que perfis limitados recebam mensagens, mas não remove nem exclui incrementos de contador.

## Definir horário de silêncio {#quiet-hours}

O **_Período de silêncio_** permite definir exclusões com base no tempo para canais de email, SMS, Push e WhatsApp. Elas garantem que nenhuma mensagem seja enviada durante períodos específicos, ajudando a respeitar as preferências do cliente e os requisitos de conformidade.

>[!NOTE]
>
>Na versão atual do Beta, somente os canais de email e WhatsApp são compatíveis com o jornada.

Você pode aplicar horas de silêncio por meio de conjuntos de regras e atribuí-las a ações de canais individuais no jornada para obter um controle preciso. Ao simplificar esses padrões, você pode aprimorar a experiência do cliente, economizar tempo e garantir a conformidade com as regras de comunicação:

* **Não desperte seu cliente** - *O cliente certo, o canal certo, a hora certa* é o mantra de muitos profissionais de marketing, portanto, faz sentido que a sincronização seja uma parte essencial da jornada do cliente. Ao definir uma regra de Período de silêncio, as marcas têm melhor controle sobre quando os contatos estão recebendo mensagens, garantindo que elas as recebam quando tiverem mais probabilidade de adotar medidas em relação à sua mensagem.
* **Conveniência** - intercepte facilmente comunicações entre campanhas e jornadas quando precisar impedir que um público receba uma mensagem sem precisar interromper toda a jornada ou campanha.
* **Economia de Tempo** - Gerencie exclusões em um local criando uma **regra baseada em tempo**, em vez de adicionar vários nós de condição com expressões personalizadas.\
  <!--* **Extra Safeguard** - Benefit from an extra safeguard in case audience criteria or time-window configurations were incorrectly set, ensuring individuals are still excluded when they should be.-->

>[!BEGINSHADEBOX]

**Medidas de proteção e limitações**

* **Atraso de propagação** - As atualizações de uma regra de horas de silêncio podem levar até 12 horas para serem aplicadas às ações de canal que já usam essa regra.
* **Latência de alto volume** - No caso de comunicações de alto volume, o sistema pode demorar mais para começar a aplicar com êxito supressões de horas silenciosas.

>[!ENDSHADEBOX]

<!--* **Custom actions** – For custom actions, only quiet hours rules are enforced. If a rule set also includes other rules (e.g., frequency capping), those rules are ignored.-->
<!--* **Pre-suppression window** – The system begins suppressing communications 30 minutes before quiet hours start, ensuring that no messages are delivered once the quiet period begins.-->

### Criar regras de horários de silêncio {#create-quiet-hour-rules}

>[!NOTE]
>
>O período de silêncio só pode ser definido em **_conjuntos de regras personalizados_**. O conjunto de regras global não oferece suporte à configuração de horas silenciosas.

1. Selecione o conjunto de regras de canal ao qual deseja adicionar a regra ou crie um novo conjunto de regras de canal.

1. Na página do conjunto de regras, clique em **[!UICONTROL Adicionar regra]** e digite um nome exclusivo para a regra.

   >[!NOTE]
   >
   > O campo _[!UICONTROL Categoria]_ especifica a categoria de mensagens para a regra. Atualmente, este campo é somente leitura e somente a categoria **[!UICONTROL Marketing]** está disponível.

1. Para o _[!UICONTROL Tipo de regra]_, selecione **[!UICONTROL Período de silêncio]**.

   ![Horas de silêncio selecionadas como o tipo de regra](./assets/business-rules-quiet-hours-rule-type.png){width="700" zoomable="yes"}

1. Na seção **[!UICONTROL Datas e horas]**, defina quando aplicar horas silenciosas:

   * Para **[!UICONTROL Fuso horário]**, escolha um fuso horário padrão para todos os destinatários no público, independentemente dos fusos horários individuais.

     Para usar o campo de fuso horário de cada perfil, selecione **[!UICONTROL Usar fuso horário local dos destinatários]**.

     >[!IMPORTANT]
     >
     >Se um perfil não tiver fuso horário, as horas de silêncio não serão aplicadas a esse perfil.

   * Clique no ícone _Calendário_ e especifique o período em que as horas de silêncio devem ser aplicadas.

     * **[!UICONTROL Semanalmente]** - Escolha dias da semana específicos e um intervalo de tempo. Você também pode aplicar a regra **[!UICONTROL O dia todo]**.

     * **[!UICONTROL Data personalizada]** - Escolha datas específicas no calendário e um intervalo de tempo. Você também pode aplicar a regra **[!UICONTROL O dia todo]**.

     ![Caixa de diálogo do calendário para definir datas e horas de silêncio](./assets/business-rules-quiet-hours-dates-times-calendar.png){width="450"}

   * Clique no botão **[!UICONTROL Adicionar mais datas]** para adicionar até cinco períodos separados.

1. Na seção **[!UICONTROL Manipulando ações durante as horas de silêncio]**, escolha como as mensagens serão tratadas durante o período selecionado:

   ![Manipulando ações durante as opções de período de silêncio](./assets/business-rules-quiet-hours-dates-times.png)

   * **[!UICONTROL Mensagem da fila]** - As mensagens são enviadas ao final do período de silêncio, a menos que estejam no estado Pausado.

     >[!NOTE]
     >
     >Se uma mensagem permanecer no estado enfileirado para um perfil por mais de 7 dias, ela será descartada.

   * **[!UICONTROL Descartar mensagem]** - As mensagens nunca são enviadas.

     >[!NOTE]
     >
     >Se você selecionar **[!UICONTROL Descartar]** e aplicar esta regra a uma ação de jornada, o perfil será removido da entrega de mensagens e sairá da jornada.

1. Clique em **[!UICONTROL Salvar]** para confirmar a criação da regra.

   Sua regra de horários de silêncio é adicionada ao conjunto de regras com o status _[!UICONTROL Rascunho]_.

1. Repita as etapas acima para adicionar quantas regras forem necessárias ao conjunto de regras.

1. Quando a regra estiver pronta para ser aplicada a mensagens, ative a regra e o conjunto de regras.

### Aplicar horas de espera a uma ação de jornada {#apply-quiet-hours}

Depois que a regra for salva e o conjunto de regras for ativado, você poderá aplicá-lo às ações de canal no jornada.

1. Ao criar uma jornada, adicione um dos [nós de ação](../marketing/action-nodes.md) de Envio para um canal que você selecionou para a regra e edite o conteúdo da mensagem.

1. Na guia _[!UICONTROL Ações]_, defina a opção **[!UICONTROL Regras de negócio]** para o conjunto de regras com a regra de horas de silêncio.

   ![Opção de regras de negócios definida para o conjunto de regras de horas de silêncio na guia Ações](./assets/business-rules-quiet-hours-email-actions.png){width="600" zoomable="yes"}

   >[!NOTE]
   >
   >Somente conjuntos de regras ativados estão disponíveis na lista.

1. Conclua e publique a jornada quando estiver pronto.
