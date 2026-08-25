---
title: Otimização do tempo de envio de email
description: Configure a otimização de tempo de envio nas jornadas pessoais do Marketo Otimizer. Defina janelas de envio, adicione nós de espera e exiba relatórios STO no Co-worker.
source-git-commit: 75b481faf0d66210329f95c8afabdfa59e7bcb79
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 0%

---

# Otimização do tempo de envio de email

Use o recurso de Otimização de hora de envio (STO) para personalizar o tempo de entrega de email para [jornadas de pessoas](./person-journeys.md), prevendo quando cada perfil tem maior probabilidade de participar. Em vez de um tempo de envio fixo, o STO usa sinais históricos de engajamento de email para agendar a entrega no horário ideal para cada recipient, melhorando o engajamento geral.

O STO analisa o engajamento histórico de cada perfil usando um grande modelo de linguagem. Ele prevê e classifica os possíveis tempos de envio e, em seguida, agenda o delivery no momento com a classificação mais alta na janela de otimização.

Os insights de desempenho, como uso, aumento de engajamento e comparações STO versus não STO, estão disponíveis por meio de consultas em linguagem natural no Co-worker.

>[!BEGINSHADEBOX]

Há muitos **_aprimoramentos futuros_** planejados para o STO:

* Configuração STO global na área _[!UICONTROL Admin]_
* Ativação de STO no nível da jornada
* Divisões de teste/controle configuráveis

>[!ENDSHADEBOX]

## Configuração {#configuration}

Você pode configurar a otimização de hora de envio ao [adicionar um nó _[!UICONTROL Executar uma ação]_](./action-nodes.md) a uma jornada de pessoa e escolher a ação **[!UICONTROL Enviar email]**.

1. Selecione o nó da ação de jornada _Enviar email_.

1. Nas propriedades do nó à direita, habilite a opção **[!UICONTROL Otimização de Tempo de Envio]**.

   ![Nó de jornada de envio de email - Opções de Otimização de Tempo de Envio](./assets/email-node-send-time-optimization.png){width="450" zoomable="no"}

1. Para especificar a janela e a distribuição de teste, defina as opções STO:

   * **[!UICONTROL Enviar no próximo]** - Esse valor determina a janela de otimização (em dias), que é o intervalo de tempo no qual os emails podem ser entregues. Por exemplo, para um webinário que ocorre em cinco dias, você pode definir uma janela de quatro ou cinco dias. O STO seleciona o melhor tempo de envio previsto para cada perfil nessa janela.

   * **STO / Distribuição fixa** - STO cria automaticamente uma _divisão de teste e controle_ para dividir perfis qualificados entre tempos de envio otimizados e fixos. A divisão permite a comparação direta de desempenho. (Aprimoramentos futuros estão planejados para permitir porcentagens divididas personalizadas.)

   >[!NOTE]
   >
   >Perfis com um histórico de engajamento forte são divididos uniformemente em grupos de controle e teste para medir o impacto do STO. Para garantir resultados estatisticamente confiáveis, a divisão STO versus não STO é restrita entre 30% e 70%. Isso ajuda a evitar que coortes menores distorçam os resultados e garante comparações significativas.

1. Diretamente após o nó _[!UICONTROL Enviar email]_, [adicionar um nó _Aguardar_](./wait-nodes.md).

   Um nó de espera deve seguir imediatamente uma ação de email habilitada para STO. A adição desse nó garante que os perfis permaneçam na jornada até que a janela de otimização completa seja limpa e todos os envios de STO sejam concluídos. Se você omitir esse nó, o sistema sinalizará a configuração como inválida.

1. Após concluir o restante da jornada de pessoas, prossiga para [publicar](./person-journeys.md#publish).

## Relatórios {#reporting}

Os dados de desempenho de STO estão disponíveis por meio do [Colaborador](../agents/chat-interface.md) usando a habilidade `send-time-report`. Você pode exibir um relatório em nível de jornada que resume todos os nós de e-mail ou detalhar um relatório em nível de nó para uma ação de e-mail específica.

O relatório exibe cada nó de email na jornada e indica se o STO está ativado para ele. Ele também mostra uma comparação tabular entre emails habilitados para STO e não STO, para que você possa avaliar o aumento de engajamento.

### Gerar o relatório STO {#generate-sto-report}

Há três maneiras de gerar um relatório STO usando o Colaborador:

**Usar o comando de barra**

1. No painel Colaborador, digite `/` para exibir a lista de habilidades disponíveis.
1. Selecione **[!UICONTROL enviar-relatório-de-tempo]** na lista e clique na seta para cima para enviar a consulta.

   ![Consulta de habilidades do relatório de tempo de envio do colaborador](./assets/email-sto-reporting-coworker.png){width="700" zoomable="yes"}

   Se uma jornada for aberta no editor, o Co-worker a usará como contexto automaticamente. Caso contrário, o Co-worker solicitará que você especifique a jornada.

   O colaborador carrega o relatório e exibe um cartão de resumo.

1. Clique em **[!UICONTROL Abrir relatório]** para exibir o relatório completo com detalhes em nível de nó.

**Clique em um nó de email**

1. Na tela de jornada, clique no nó **[!UICONTROL Enviar email]**.

1. No painel Colaborador, solicite o relatório STO.

   Como o nó é selecionado, o Co-worker o usa como contexto e retorna um relatório com escopo somente para esse nó.

   Ele carrega o relatório e exibe um cartão de resumo.

1. Clique em **[!UICONTROL Abrir relatório]** para exibir o relatório completo.

**Consulta de linguagem natural**

1. No painel Colaborador, insira uma solicitação como _Dê-me o relatório STO para [nome da jornada]_.

   O colaborador interpreta a solicitação, carrega a habilidade `send-time-report`, gera o relatório e exibe um cartão de resumo.

1. Clique em **[!UICONTROL Abrir relatório]** para exibir o relatório completo.

### Exibir os dados do relatório de email {#sto-report-data}

Você pode reduzir o painel Colaborador para aumentar o tamanho do relatório exibido ou rolar a tela para ver a largura total.

![Relatório de otimização de hora de envio - resumo do desempenho do email](./assets/email-sto-reporting-summary-report.png){width="700" zoomable="yes"}

Na coluna _[!UICONTROL Detalhes]_, clique em **[!UICONTROL Exibir resultados STO]** para abrir uma janela pop-up. A janela fornece visualizações de dados de email para _Comparação de desempenho_, _Distribuição de tempo de envio_ e _Integridade de dados_.

![Relatório de otimização de hora de envio - dados de desempenho de email](./assets/email-sto-reporting-data.png){width="500" zoomable="yes"}
