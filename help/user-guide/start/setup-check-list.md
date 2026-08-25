---
title: Lista de verificação de configuração
description: Conclua as tarefas de configuração iniciais para sua instância do Marketo Otimizer, incluindo a configuração de acesso do usuário e a infraestrutura de capacidade de entrega de email.
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 10%

---

# Lista de verificação de configuração

Conclua essas tarefas para habilitar a funcionalidade na instância [!DNL Marketo Optimizer] provisionada.

## Habilitar acesso do usuário {#enable-user-access}

Quando o provisionamento estiver concluído e as sandboxes estiverem vinculadas, configure o acesso do [!DNL Journey Optimizer B2B Edition] para sua equipe e usuários.

<table>
<thead>
<tr>
<th colspan="2">Tarefa</th>
<th>Detalhes e instruções</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong>Fornecer acesso e permissões ao produto</strong> para usuários</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Caixa de seleção para tarefa"/></td>
<td>Criar um perfil de produto do Journey Optimizer B2B edition na Admin Console (configuração única/inicial apenas)</td>
<td><a href="./user-management.md#create-profile">Criar perfil</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Caixa de seleção para tarefa"/></td>
<td>Adicionar um grupo de usuários na Admin Console</td>
<td><a href="./user-management.md#add-user-group">Adicionar grupo de usuários</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Caixa de seleção para tarefa"/></td>
<td>Atribuir o perfil de produto ao grupo de usuários no Admin Console</td>
<td><a href="./user-management.md#assign-profile">Atribuir perfil de produto</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Caixa de seleção para tarefa"/></td>
<td>Adicionar usuários ao grupo de usuários no Admin Console</td>
<td><a href="./user-management.md#add-users">Adicionar usuários</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Caixa de seleção para tarefa"/></td>
<td>Editar funções integradas ou criar uma função personalizada com permissões de produto</td>
<td><a href="./user-management.md#edit-role-permissions">Editar funções</a> <br/> <a href="./user-management.md#create-a-custom-role">Criar uma função personalizada</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Caixa de seleção para tarefa"/></td>
<td>Adicionar usuários ou grupos a funções no Adobe Experience Platform</td>
<td><a href="./user-management.md#add-users-to-a-role">Adicionar usuários</a> <br/><a href="./user-management.md#add-user-groups-to-a-role">Adicionar grupos</a></td>
</tr>
</tbody>
</table>

## Capacidade de entrega de email {#email-deliverability}

Antes que os profissionais de marketing possam enviar emails do jornada, configure a infraestrutura de envio para sua organização, incluindo a delegação de subdomínio, a autenticação de email e as configurações de canal.

<table>
<thead>
<tr>
<th colspan="2">Tarefa</th>
<th>Detalhes e instruções</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong>Definir configurações de capacidade de entrega de email e canal</strong></td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Caixa de seleção para tarefa"/></td>
<td>Delegar um subdomínio à Adobe (totalmente delegado ou CNAME)</td>
<td><a href="./email-deliverability.md#delegate-fully-delegated">Totalmente delegado</a> <br/> <a href="./email-deliverability.md#delegate-cname">CNAME</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Caixa de seleção para tarefa"/></td>
<td>Configurar o DMARC para o subdomínio</td>
<td><a href="./email-deliverability.md#configure-dmarc">Configurar DMARC</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Caixa de seleção para tarefa"/></td>
<td>Revisar e atribuir um pool de IPs</td>
<td><a href="./email-deliverability.md#review-ip-pool">Revisar pool de IPs</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Caixa de seleção para tarefa"/></td>
<td>Criar uma configuração de canal de email</td>
<td><a href="../admin/email-channel-configuration.md#create-email-channel-configuration">Configurar canal de email</a></td>
</tr>
</tbody>
