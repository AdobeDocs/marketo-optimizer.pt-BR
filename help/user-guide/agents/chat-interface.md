---
title: Interface de chat
description: Use o painel de chat do Colaborador no Marketo Otimizer para criar programas, jornadas e listas usando a linguagem natural ou o menu de barra (/).
source-git-commit: 75b481faf0d66210329f95c8afabdfa59e7bcb79
workflow-type: tm+mt
source-wordcount: '859'
ht-degree: 0%

---

# Interface de chat

O painel de chat está incorporado em todo o [!DNL Adobe Marketo Optimizer]. É onde você interage com os agentes de IA usando linguagem simples para criar programas e jornadas, criar e comparar listas de pessoas, investigar leads, configurar pontuação e muito mais.

Selecione o ícone de _Colaborador_ na navegação à esquerda para abrir o painel. O cabeçalho do painel tem quatro controles:

| Controle | Descrição |
|---------|-------------|
| **Nova conversa** | Iniciar um novo bate- papo (limpa a discussão atual). |
| **Histórico da conversa** | Abrir conversas passadas para que você possa reabrir uma. |
| **Trocar painéis** | Mova o painel de chat para o outro lado do espaço de trabalho. |
| **Recolher** | Oculte o painel para dar mais espaço ao espaço de trabalho. |

Na parte inferior do painel há uma caixa de mensagem na qual é possível:

* Adicione uma mensagem e pressione **Enter** para enviar (**Shift+Enter** insere uma nova linha).
* Anexe um arquivo usando o ícone _Anexar_ (formatos com suporte: `.txt`, `.md`, `.csv`, `.json`, `.xlsx`, `.docx`, `.pdf`). Use carregamentos de CSV e planilhas para iniciar uma importação de clientes potenciais.

## Pergunte ao colega de trabalho

Há duas maneiras igualmente válidas de fazer um trabalho — você nunca precisa usar o menu de barras.

**Linguagem natural** — digite sua solicitação da maneira que você diria a um colega:

* _&quot;Crie uma jornada de boas-vindas para novas inscrições em avaliação.&quot;_
* _&quot;Por que o john@acme.com não inseriu esta jornada?&quot;_
* _&quot;Comparar minhas listas &#39;Participantes do webinário do 3º trimestre&#39; e &#39;Contas da empresa&#39;.&quot;_

O agente corresponde sua redação à habilidade correta nos bastidores e executa o fluxo de trabalho apropriado.

**O menu de barra invertida (/)** — Digite `/` para abrir um menu navegável de tudo o que o Co-worker pode fazer. Isso é útil quando você deseja descobrir recursos ou ir diretamente para um fluxo de trabalho conhecido.

## O menu de barra (/)

Use um `/` no início da caixa de mensagem ou depois de um espaço para abrir o menu. À medida que você continua digitando, a lista filtra por nome, descrição ou ID — por exemplo, `/journey` limita-se a comandos relacionados à jornada.

Use **/** para percorrer as entradas, **Enter** ou **Tab** para selecionar e **Esc** para ignorar. Você também pode clicar diretamente em uma entrada.

As entradas de menu são agrupadas em seções rotuladas:

| Seção | Contém |
|---------|----------|
| **Investigar** | Pesquisas de diagnóstico somente leitura (por exemplo, investigação de cliente potencial, consultas de intenção). |
| **Validar** | Controle de qualidade e fluxos de trabalho de auditoria. |
| **Compilação** | Fluxos de trabalho de criação (programas, jornadas, listas, pontuação). |
| **Importar** | Importação de clientes em potencial do CSV. |
| **Outras** | Qualquer coisa que não se encaixe nas categorias acima. |

O menu também lista **conectores** (por exemplo, _Procurar no Marketo_ abre uma caixa de diálogo do seletor) e **atalhos de navegação** que levam você para uma tela de espaço de trabalho.

### Selecionar um item de menu

Quando você seleciona uma habilidade ou agente no menu, um prompt inicial é inserido na caixa de mensagem para você editar - ela **não** é enviada automaticamente. Por exemplo, selecionar _Planejar campanhas_ cai em _&quot;Planejar um novo programa do Marketo para [nome da campanha]. Carregarei o resumo.&quot;_ Preencha os espaços reservados entre colchetes e pressione **Enter** para enviar.

Os conectores abrem uma modal em vez de inserir texto. Os atalhos de navegação levam você diretamente para essa tela no espaço de trabalho.

>[!NOTE]
>
>Alguns comandos aparecem esmaecidos e marcados como _Em breve_. Eles são limitados por sinalizadores de recursos e ainda não estão ativos para sua conta — selecionar um não faz nada. O conjunto disponível depende de quais recursos estão habilitados para você.

## Habilidades

Uma habilidade é um fluxo de trabalho empacotado que o agente sabe executar — os blocos fundamentais por trás das solicitações do menu `/` e de linguagem natural. Cada habilidade contém instruções passo a passo e as ferramentas específicas necessárias para um trabalho (por exemplo, &quot;publicar uma jornada&quot;, &quot;comparar duas listas de pessoas&quot;, &quot;criar um modelo de pontuação&quot;).

Consulte _[Habilidades do colaborador](./skills.md)_ para obter uma lista completa das habilidades atualmente permitidas.

Principais informações sobre habilidades:

* **As habilidades têm escopo de produto.** No [!DNL Marketo Optimizer] você verá várias habilidades específicas do produto (jornadas, listas de pessoas, pontuação, canais, otimização de tempo de envio etc.). Algumas habilidades são somente [!DNL Marketo Engage] e algumas trabalham nos dois produtos (importação de clientes potenciais, conhecimento do produto). Você só vê habilidades relevantes para onde você está.
* **Não é necessário decorar nomes de habilidades.** Descreva sua meta e o agente escolhe a habilidade correspondente. O menu `/` é um atalho mais rápido e detectável para os mesmos fluxos de trabalho.
* **Algumas habilidades só são lidas; outras mudam as coisas.** Habilidades de investigação e de relatório (por exemplo, investigação de cliente potencial, consulta de intenção, relatório de hora de envio) somente leitura de dados. Crie e configure habilidades (por exemplo, criação de jornada, pontuação) para criar ou alterar dados.

## Prompts de acompanhamento

Após as respostas do Colaborador, ele geralmente mostra uma linha de prompts de acompanhamento clicáveis adaptados ao que você acabou de fazer. Por exemplo, depois de criar uma jornada, ele pode oferecer _&quot;Publicar esta jornada&quot;_ ou _&quot;Adicionar uma etapa de espera&quot;_. Clique em um para continuar sem digitar. Estas são apenas sugestões; você sempre pode digitar sua própria próxima mensagem em vez disso.

## Dicas

* **Ser específico com identificadores.** Ao investigar ou editar, inclua o endereço de email, o nome da pessoa, o nome da jornada ou o nome da lista para que o agente atue no ativo correto.
* **Use `/` para explorar.** Se não tiver certeza do que o Colaborador pode fazer, abra o menu `/` e ignore as categorias.
* **Editar o prompt inicial.** Selecionar uma habilidade fornece um modelo — substitua os espaços reservados `[bracketed]` antes de enviar.
* **Carregar primeiro para importações.** Para uma importação de clientes potenciais, primeiro anexe o CSV e, em seguida, descreva o que deseja fazer com ele.
* **Iniciar uma nova conversa** ao alternar para uma tarefa não relacionada, portanto, o contexto anterior não afeta a nova solicitação.
