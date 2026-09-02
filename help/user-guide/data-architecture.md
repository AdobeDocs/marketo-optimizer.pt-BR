---
title: Arquitetura de alto nível
description: Saiba mais sobre a arquitetura de dados que conecta o Marketo Otimizer e o Marketo Engage, incluindo sincronização bidirecional, latência de entidade e isolamento de dados do locatário.
role: User, Admin
source-git-commit: ef30aa7a901c18c7b9b0919d537ad59db9a6c481
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 1%

---


# Arquitetura de alto nível

[!DNL Adobe Marketo Optimizer] integra-se com [!DNL Adobe Marketo Engage] para fornecer uma visão de 360 graus de clientes potenciais B2B. Uma sincronização bidirecional e confiável mantém o [!DNL Marketo Engage] e o [!DNL Marketo Optimizer] alinhados, dando às duas plataformas uma visão única e compartilhada de Pessoas, Empresas, Objetos Personalizados e Atividades. O fluxo de dados de alto desempenho quase em tempo real garante que os registros permaneçam atuais e acionáveis, para que campanhas e jornadas possam responder aos clientes potenciais no momento em que interagem.

## Base de dados

[!DNL Marketo Optimizer] e [!DNL Marketo Engage] compartilham uma base de dados comum que os mantém sincronizados enquanto alimentam análises downstream.

![Diagrama do Marketo Otimizer e da arquitetura do Marketo Engage que mostra como os serviços, os tempos de execução e os armazenamentos de dados dos dois produtos se conectam pela Microsoft Azure e pela AWS](./assets/marketo-optimizer-architecture.svg)

Em um alto nível:

* **[!DNL Marketo Engage]Core** é a fonte definitiva para dados de cliente potencial e objeto personalizado, garantindo a integridade dos dados no ponto de captura.
* Uma **camada do Data Broker** coordena como os dados se movem entre [!DNL Marketo Engage] e [!DNL Marketo Optimizer], agregando dados compartilhados e replicados em um ambiente operacional pronto para uso. Toda essa troca é executada em uma única instância compartilhada do AWS Aurora, formando a base de ciclo fechado para a orquestração B2B de alta escala.
* **As atividades** seguem um caminho definido: são gravadas primeiro no banco de dados [!DNL Marketo Engage] e indexadas no Apache SOLR para pesquisa rápida no produto e, em seguida, publicadas no pipeline de atividade para que [!DNL Marketo Optimizer] tenha reconhecimento instantâneo. O tempo de execução do jornada processa essa atividade e a grava no Snowflake, transformando os dados operacionais em um estado pronto para análise. A partir daí, a atividade é replicada em [!DNL Adobe Experience Platform] conjuntos de dados e [!DNL Adobe Customer Journey Analytics] para gerar relatórios.
* Diferentes tipos de entidades sincronizam em diferentes velocidades e direções para equilibrar a atualização com a integridade do sistema:

| Entidade [!DNL Marketo Engage] | Direção da sincronização | Latência |
| --- | --- | --- |
| Lead | Bidirecional | &lt; 1 s |
| Empresa | Bidirecional | &lt; 1 s |
| Objeto personalizado | Unidirecional | &lt; 5 s |
| Atividade | Unidirecional | &lt; 5 s |
| associação ao programa | Não sincronizado | — |
| Ativos | Não sincronizado | — |

Clientes potenciais e empresas atualizam instantaneamente em ambas as direções, sem criar cópias de dados duplicadas. Os Objetos Personalizados são replicados em segundos, portanto, as atualizações de esquema em [!DNL Marketo Engage] são imediatamente acionáveis em uma jornada ativa. A associação ao programa e o Assets são intencionalmente excluídos da sincronização para preservar a velocidade e a integridade do sistema.

Esse design de latência quase zero significa que os painéis de análise e os sistemas downstream são alimentados em tempo quase real, permitindo a otimização de campanhas ativas e o acompanhamento rápido de leads de alta prioridade.

### Isolamento e locação de dados

* Os dados do cliente são compartilhados entre [!DNL Marketo Engage], [!DNL Marketo Optimizer] e [!DNL Experience Platform] como parte da sincronização de dados do produto e da arquitetura de análise.
* Os dados são isolados logicamente por locatário e protegidos pelos controles de segurança da Adobe.
* Os dados são transferidos em canais seguros e criptografados e armazenados nos serviços gerenciados pela Adobe usando criptografia e controles de acesso padrão do setor.
* Dependendo do tipo de dados, as informações podem ser sincronizadas entre [!DNL Marketo Engage] e [!DNL Marketo Optimizer] ou replicadas para [!DNL Experience Platform] para oferecer suporte aos recursos de relatórios e análises, mantendo a segurança e o isolamento do locatário.
