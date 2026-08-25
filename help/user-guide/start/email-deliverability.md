---
title: Configuração da entregabilidade de email
description: Configure pools de delegação de subdomínio, DMARC, SPF, DKIM e IP para o Marketo Otimizer.
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '2502'
ht-degree: 0%

---

# Capacidade de entrega de email

As informações a seguir são para administradores que configuram a infraestrutura de envio para suportar profissionais de marketing e criadores de conteúdo de email. Ele descreve recursos de entrega e como configurar subdomínios, autenticação e pools de IP.

A capacidade de entrega de emails no [!DNL Adobe Marketo Optimizer] é o conjunto de configurações de infraestrutura e autenticação que ajudam as mensagens de email a chegar à caixa de entrada do destinatário, não à pasta de spam, e não bloqueadas pelos ISPs (Provedores de Serviços de Internet).

Ele usa os seguintes blocos fundamentais, configurados por um administrador, normalmente na seguinte ordem:

1. [Delegar um ou mais subdomínios](#subdomain-delegation) à Adobe.
1. [Configurar registros do DMARC, SPF e DKIM](#dmarc-spf-dkim) em cada subdomínio.
1. [Confirme o pool de IPs](#ip-pools) usado para enviar emails para o subdomínio.
1. [Crie uma ou mais configurações de canal de email](../admin/email-channel-configuration.md#create-email-channel-configuration) que associam um subdomínio, um pool de IPs e uma identidade de remetente.

![Configuração da capacidade de entrega de emails do Marketo Otimizer](./assets/email-deliverability-diagram.svg){width="550" zoomable="yes"}

>[!TIP]
>
>Trate a capacidade de entrega e a configuração do canal como uma atividade de administrador única. Quando configurados, os profissionais de marketing e autores de email não precisam revisitá-los.
>
> Consulte os seguintes tópicos para obter informações adicionais sobre canais de email:
>
>* Configurando canais de email - [Configuração de canal de email](../admin/email-channel-configuration.md)
>* Criando emails - [Adicionar emails ao jornada](../marketing/email-channel.md)
>* Criando conteúdo de email - [Criação de conteúdo de email](../content/email-authoring.md)

## Limitações atuais {#limitations}

* **O método de delegação personalizado** para delegação de subdomínio ainda não está disponível. Use Totalmente delegado ou CNAME. A delegação personalizada está direcionada para a versão do GA.
* **Pools de IP dedicados** não estão disponíveis na Beta. O pool de IPs compartilhados é a única opção. IPs dedicados enviados na GA, incluindo planejamento de aquecimento de IP e gerenciamento de registros PTR.

## Principais conceitos {#key-concepts}

Antes de configurar o email, analise esses conceitos que se aplicam aos recursos de capacidade de entrega de canal de email:

| Conceito | O que significa em [!DNL Marketo Optimizer] |
| ------- | ---------------------- |
| **_Subdomínio_** | Uma parte delegada do seu domínio de envio (por exemplo, `mail.contoso.com`) usada para enviar emails por meio de [!DNL Marketo Optimizer]. Os subdomínios isolam sua reputação de marketing B2B do correio corporativo ou transacional. |
| **_Pool de IPs_** | Um grupo de endereços IP associados a um ou mais subdomínios. O [!DNL Marketo Optimizer] oferece suporte a um pool de IPs compartilhados gerenciado pela Adobe nesta versão; os pools de IP dedicados estão no roteiro de disponibilidade geral. |
| **_Configuração de canal_** | Um conjunto reutilizável de configurações de envio de email (identidade do remetente, endereço de resposta, subdomínio, pool de IPs, tipo de email e rastreamento) que você anexa às ações de email no jornada. É possível ter várias configurações de canal nomeadas para diferentes marcas, unidades de negócios ou tipos de envio. |

<!--

## Roles and permissions {#roles-permissions}

[!DNL Marketo Optimizer] uses role-based access control (RBAC) for email features. Permissions are managed in the Adobe Admin Console (IMS) and synced at login. Product administrators assign granular permissions to product profiles, and then attach those product profiles to users.

Access to email functionality in [!DNL Marketo Optimizer] is gated by two layers:

1. **Feature flag (LD).** A LaunchDarkly flag controls whether the entire feature is turned on for your organization. Email authoring and deliverability are gated by `dx_ajo_btob_channel_foundation`. Without this flag, the feature is hidden regardless of permissions.
2. **Functional permission.** A user-level permission that controls whether a specific user can read or write within a feature.

Most email features follow a `view-*` (read) and `manage-*` (write) pattern. A user needs the read permission to see a feature in the navigation, and the write permission to create, edit, or delete within it.

### Email authoring permissions {#email-authoring-permissions}

| Capability | Permission | What it allows |
| ---------- | ---------- | -------------- |
| **View emails** | `view-b2b-emails` | View the email list, open emails, view content (read-only). |
| **Create / edit / delete emails** | `manage-b2b-emails` | All read access plus create, edit, duplicate, and delete emails. Required to author email content within a journey. |
| **View templates** | `view-b2b-templates` | Browse and preview templates in the Templates gallery (read-only). |
| **Create / edit / delete templates** | `manage-b2b-templates` | All read access plus create, edit, and delete saved templates. |
| **View fragments** | `view-b2b-fragments` | Browse and preview visual fragments (read-only). |
| **Create / edit fragments** | `manage-b2b-fragments` | All read access plus create and edit visual fragments. |
| **Publish fragments** | `publish-b2b-fragments` | Publish a fragment so it becomes available to email authors across the organization. |
| **Manage shared assets and library items** | `manage-b2b-library-items` | Manage the underlying shared library used by templates, fragments, and emails. Often granted alongside the template/fragment manage permissions. |
| **Manage usage labels** | `manage-b2b-delete-usage-labels` | Manage data usage labels (DULE) attached to library items for governance. |
| **Manage packages** | `manage-b2b-packages` | Bundle and move templates, fragments, and emails between sandboxes. |
| **View assets (Marketo Design Studio assets in [!DNL Marketo Optimizer])** | `view-b2b-assets` | Browse the asset picker and preview images. Read-only. |
| **Manage assets** | `manage-b2b-assets` | All read access plus future asset-management actions (Beta scope). |
| **Export message data** | `manage-b2b-message-export` | Export email-level message data and reports. |

Within a person journey, the **Send email** action requires `manage-b2b-person-journeys` (to add the action and activate the journey). A user with only email permissions can author content but cannot add an email to a journey.

### Email deliverability permissions {#email-deliverability-permissions}

Deliverability features (subdomains, DMARC, IP pools, suppression lists, allowed lists, IP warmup plans, and seed lists) are administrator-level configuration. They are governed by two permissions covering the entire **[!UICONTROL Channels]** > **[!UICONTROL Email settings]** area:

| Capability | Permission | What it allows |
| ---------- | ---------- | -------------- |
| **View email settings** | `view-b2b-email-settings` | View subdomains, PTR records, IP pools, suppression list, allowed list, IP warmup plans, and seed lists (read-only). |
| **Manage email settings** | `manage-b2b-email-settings` | All read access plus delegate subdomains, configure DMARC, manage suppression and allowed lists, manage IP warmup plans and seed lists. |

Some sub-features within Email settings are gated by additional LaunchDarkly flags — Suppression list (`enable-suppression`), Allowed list (`enable-allow-list`), Seed lists (`enable-seedlist-ui`). If a sub-feature is not visible in your organization, check with your Adobe representative on flag enablement.

### Channel configuration permissions {#channel-configuration-permissions}

Channel configurations sit under **[!UICONTROL Channels]** → **[!UICONTROL General settings]**. They tie deliverability primitives (subdomain, IP pool, sender identity) to a reusable object that journey authors reference. They are governed by a single permission:

| Capability | Permission | What it allows |
| ---------- | ---------- | -------------- |
| **Manage channel configurations** | `manage-b2b-channels-configurations` | View, create, edit, and delete email channel configurations. |

-->

## Delegação de subdomínios {#subdomain-delegation}

A delegação de subdomínio informa à Internet que a Adobe está autorizada a enviar emails em nome de um subdomínio específico (por exemplo, `mail.contoso.com`) do seu domínio. Delegar um subdomínio dedicado — em vez do domínio raiz — protege o e-mail corporativo e oferece os seguintes benefícios:

* **Isolamento de reputação.** Os envios de marketing são mantidos separados do correio corporativo. Se a reputação de marketing cair, seu email transacional e corporativo não será afetado.
* **Aquecimento de IP mais rápido.** Subdomínios dedicados ajudam a estabelecer uma reputação positiva do remetente mais rapidamente com ISPs.
* **Autenticação moderna.** O SPF, o DKIM e o DMARC podem ser configurados corretamente por subdomínio sem afetar outros fluxos de email.
* **Conformidade.** Ajuda a atender aos requisitos de remetentes em massa do Gmail, Yahoo e outros principais ISPs.

>[!NOTE]
>
>Cada subdomínio em [!DNL Marketo Optimizer] só pode ser usado por um produto Adobe. Você não pode compartilhar o mesmo subdomínio de envio entre [!DNL Marketo Optimizer] e outro produto, como o Adobe Marketo Engage ou o Adobe Campaign — você deve usar subdomínios distintos.

### Métodos compatíveis {#supported-methods}

O [!DNL Marketo Optimizer] oferece suporte a dois dos três métodos de delegação de subdomínio nesta versão do Beta. O terceiro método (delegação personalizada) está no roteiro.

| Método | Quando usar | O que isso envolve |
| ------ | ----------- | ---------------- |
| **Totalmente Delegado** | Recomendado | Delegar autoridade DNS completa para o subdomínio à Adobe. O Adobe cria e mantém registros MX, SPF, DKIM, DMARC, A e CNAME. Menor sobrecarga operacional. O Adobe lida com as alterações de DNS para você. |
| **CNAME** | Para políticas restritas | Mantenha a autoridade DNS do seu lado e crie registros CNAME apontando para registros gerenciados pela Adobe. Use isso quando a política DNS da organização não permitir delegação completa. Você é responsável por manter os registros DNS. |
| **Delegação personalizada** | Roteiro (GA) | Mantenha a propriedade total dos certificados DNS e SSL. Fornece controle máximo, incluindo a capacidade de usar seus próprios certificados. Ele é direcionado para a versão do GA. |

### Delegar um subdomínio (método totalmente delegado) {#delegate-fully-delegated}

>[!PREREQUISITES]
>
>* Decida sobre uma convenção de nomenclatura de subdomínio (por exemplo, `mail.contoso.com` para marketing, `alerts.contoso.com` para transacional).
>* Confirme com a equipe de TI/DNS que eles podem delegar o subdomínio (registros NS) à Adobe.
>* Crie o novo subdomínio em seu provedor de DNS e aguarde de de 24 a 48 horas pela propagação de DNS antes de delegar à Adobe.
>* Confirme se você tem a função de Administrador no [!DNL Marketo Optimizer].

1. Na navegação à esquerda [!DNL Marketo Optimizer], expanda **[!UICONTROL Administração]** e selecione **[!UICONTROL Canais]**.
1. No painel, expanda **[!UICONTROL Configurações de email]** e selecione **[!UICONTROL Subdomínios]**.
1. Clique em **[!UICONTROL Configurar subdomínio]**.
1. Insira o nome completo do subdomínio (por exemplo, `mail.contoso.com`).
1. Escolha **[!UICONTROL Totalmente Delegado]** como o método de delegação.
1. Configure o DMARC para o subdomínio (consulte [DMARC, SPF e DKIM](#dmarc-spf-dkim)).

   No mínimo, configure um registro do DMARC com uma política inicial de `none` para que você possa monitorar relatórios sem afetar a entrega.

1. Revise a lista de registros DNS para o Adobe gerenciar.

   Normalmente, eles incluem registros MX, SPF, DKIM, DMARC, A e CNAME (para rastreamento e URLs de mirror page).

1. Baixe os registros DNS como um arquivo CSV usando o botão **[!UICONTROL Baixar registros]**. Compartilhe este arquivo com a equipe de DNS.

1. A equipe de DNS adiciona os registros NS na solução de hospedagem de domínio que delega o subdomínio à Adobe.

1. Depois que sua equipe de DNS confirmar que os registros estão em vigor, volte para [!DNL Marketo Optimizer] e marque a caixa confirmando que você criou os registros necessários no site de hospedagem.

1. Clique em **[!UICONTROL Enviar]** para iniciar uma série de verificações de validação (pré-validação, MX, SPF, DKIM, DMARC, registro FBL).

1. Aguarde o status do subdomínio mudar para **[!UICONTROL Sucesso]**.

   Normalmente, isso leva alguns minutos após a conclusão da propagação de DNS.

>[!NOTE]
>
>Se a validação falhar, o status será alterado para **[!UICONTROL Falha]** e [!DNL Marketo Optimizer] exibirá o motivo (por exemplo, registro NS não encontrado, registro MX ausente ou DMARC configurado incorretamente). Corrija o problema de DNS subjacente e tente enviar novamente.

### Delegar um subdomínio (método CNAME) {#delegate-cname}

Use esse método somente se a política DNS da organização proibir a delegação completa. Com o CNAME, você mantém registros de DNS da sua parte.

1. Na navegação à esquerda [!DNL Marketo Optimizer], expanda **[!UICONTROL Administração]** e selecione **[!UICONTROL Canais]**.
1. No painel, expanda **[!UICONTROL Configurações de email]** e selecione **[!UICONTROL Subdomínios]**.
1. Clique em **[!UICONTROL Configurar subdomínio]**.
1. Insira o nome completo do subdomínio.
1. Escolha **[!UICONTROL CNAME]** como o método de delegação.
1. Configure o DMARC para o subdomínio ([DMARC, SPF e DKIM](#dmarc-spf-dkim)).
1. Revise a lista de registros CNAME a serem gerados. Eles apontam os componentes do subdomínio para registros gerenciados pela Adobe.
1. Baixe os registros como CSV e compartilhe com a equipe DNS.
1. A equipe de DNS adiciona cada registro CNAME à solução de hospedagem de DNS.
1. Quando os registros estiverem no local e forem propagados, volte para [!DNL Marketo Optimizer] e confirme.
1. Clique em **[!UICONTROL Enviar]**.
1. Aguarde o status alcançar **[!UICONTROL Sucesso]**.

>[!IMPORTANT]
>
>Com o CNAME, a Adobe não pode ajudar você a alterar, manter ou solucionar problemas do DNS para o subdomínio. Quaisquer alterações futuras, como a adição de um novo CNAME para uma atualização de recurso, devem ser feitas pela equipe de DNS.

Para obter instruções passo a passo para provedores DNS comuns, consulte as seguintes seções:

### Adicionar registros CNAME pelo provedor de DNS {#add-cname-records-dns-provider}

O [!DNL Marketo Optimizer] gera os registros CNAME e TXT exatos para o seu subdomínio e permite que você os baixe como um arquivo CSV. Use as seguintes etapas específicas do provedor para ajudar sua equipe de DNS a localizar a tela de configurações correta e adicionar cada registro.

>[!NOTE]
>
>Os valores de host, tipo e destino no CSV baixado são específicos para seu subdomínio e organização. Copie-os exatamente em vez de reutilizar valores de outro subdomínio.

#### Rota AWS 53 {#aws-route-53}

1. Entre no Console de Gerenciamento do AWS e abra **[!UICONTROL Rota 53]**.
1. Selecione **[!UICONTROL Zonas hospedadas]** e escolha a zona hospedada para seu domínio.
1. Clique em **[!UICONTROL Criar registro]** e mantenha a política de roteamento definida como **[!UICONTROL Roteamento simples]**.
1. Para cada linha no CSV:

   * **Nome do registro** — Insira somente a parte antes do nome da zona. Por exemplo, para `data.mail.contoso.com` na zona `contoso.com`, digite `data.mail`.
   * **Tipo de registro** — Escolha `CNAME` ou `TXT` para corresponder ao CSV.
   * **Valor** — Cole o destino do CSV. Para registros TXT, coloque o valor entre aspas duplas.
   * **TTL** — 300 segundos é suficiente.

1. Clique em **[!UICONTROL Adicionar outro registro]** às entradas de lote e em **[!UICONTROL Criar registros]** depois que todas as linhas forem inseridas.

>[!NOTE]
>
>Os valores TXT devem estar entre aspas duplas ou o registro não será validado. Um registro CNAME não pode ficar no ápice da zona, mas isso não afeta um subdomínio delegado.

#### Cloudflare {#cloudflare}

1. Faça logon no painel do Cloud e selecione seu domínio.
1. Vá para **[!UICONTROL Registros DNS]** e clique em **[!UICONTROL Adicionar registro]**.
1. Para cada linha no CSV:

   * **Tipo** — Escolha `CNAME` ou `TXT`.
   * **Nome** — Insira a parte do host, por exemplo `data.mail`. O Cloud Flare anexa seu domínio automaticamente.
   * **Target** (para CNAME) ou **Content** (para TXT) — cole o valor do CSV.
   * **Status do proxy** — Defina como **[!UICONTROL DNS somente]** (ícone cinza da nuvem).
   * **TTL** — Deixar como **[!UICONTROL Auto]**.

1. Clique em **[!UICONTROL Salvar]** para cada linha.

>[!IMPORTANT]
>
>Todos os registros adicionados para [!DNL Marketo Optimizer] devem mostrar uma nuvem cinza (somente DNS), não uma nuvem laranja (com proxy aplicado). Um registro com proxy roteia o tráfego pelos servidores da Cloud Flare em vez do Adobe, o que interrompe a assinatura do DKIM, o rastreamento de cliques e o tratamento de rejeição. Se um registro for exibido em laranja, clique no ícone de nuvem para alterná-lo para cinza.

#### DNS do Azure {#azure-dns}

1. Entre no portal do Azure e abra **[!UICONTROL zonas DNS]**.
1. Selecione a zona DNS para o seu domínio.
1. Clique em **[!UICONTROL + Conjunto de registros]**.
1. Para cada linha no CSV:

   * **Nome** — Insira a parte do host, por exemplo `data.mail`. O Azure anexa o nome da região.
   * **Tipo** — Escolha `CNAME` ou `TXT`.
   * Para um registro CNAME, insira o destino do CSV no campo **[!UICONTROL Alias]**.
   * Para um registro TXT, cole o valor no campo **[!UICONTROL Value]**. O Azure cuida das cotações para você.
   * **TTL** — Insira um número e uma unidade, por exemplo, 300 segundos.

1. Clique em **[!UICONTROL OK]** para salvar o conjunto de registros para cada linha.

>[!NOTE]
>
>Use um conjunto de registros CNAME padrão, não a opção Conjunto de registros Alias, que aponta somente para recursos do Azure, em vez de nomes de host externos. Cada conjunto de registros CNAME contém exatamente um destino, correspondendo a como [!DNL Marketo Optimizer] registros de problemas — um CNAME por host.

#### DNS da Google Cloud {#google-cloud-dns}

1. Abra o console Google Cloud e vá para **[!UICONTROL Serviços de Rede]** > **[!UICONTROL DNS de Nuvem]**.
1. Selecione a zona do domínio.
1. Clique em **[!UICONTROL Adicionar padrão]** para adicionar um conjunto de registros.
1. Para cada linha no CSV:

   * **Nome DNS** — Insira a parte do host, por exemplo `data.mail`. O DNS da nuvem mostra o sufixo da zona e você anexa o host.
   * **Tipo de registro de recurso** — Escolha `CNAME` ou `TXT`.
   * **TTL** — 300 segundos é suficiente.
   * Para um registro CNAME, insira o destino em **[!UICONTROL Nome canônico]** e termine-o com um ponto à direita.
   * Para um registro TXT, cole o valor no campo de dados.

1. Clique em **[!UICONTROL Criar]** para cada linha.

>[!NOTE]
>
>O nome canônico deve ser totalmente qualificado e terminar com um ponto à direita ou a resolução falha. Sua equipe de DNS também pode adicionar cada registro com o comando `gcloud dns record-sets create`.

### Medidas de proteção de subdomínio {#subdomain-guardrails}

* **Limite padrão:** 10 subdomínios por organização. Entre em contato com seu representante da Adobe se precisar de mais (até 100, dependendo do contrato).
* **Propagação de DNS:** Permita que as alterações ocorram de 24 a 48 horas globalmente. A validação pode falhar simplesmente porque o DNS ainda não se propagou.
* **Reutilização de subdomínio:** Um subdomínio que já está sendo usado por outro produto da Adobe (Marketo Engage, Adobe Campaign) não pode ser reutilizado em [!DNL Marketo Optimizer].

## DMARC, SPF e DKIM {#dmarc-spf-dkim}

DMARC, SPF e DKIM são padrões de autenticação de email. Juntos, eles provam aos servidores de email de recebimento que sua mensagem é realmente enviada em nome de seu domínio e não foi falsificada. ISPs modernos — Gmail, Yahoo, Microsoft — exigem esses padrões para remetentes em massa.

| Registro | Significa | Finalidade |
| ------ | ---------- | ------- |
| **SPF** | Estrutura de Política do Remetente | Lista os IPs do servidor de email permitidos para enviar emails do seu domínio. O recebimento de servidores rejeita emails de IPs que não estão nesta lista. O Adobe cria e mantém o registro SPF automaticamente ao delegar um subdomínio (Totalmente delegado). |
| **DKIM** | Email identificado de DomainKeys | Uma assinatura criptográfica adicionada a cada email de saída. O servidor de recebimento verifica a assinatura em relação a uma chave pública publicada no DNS. O Adobe gera automaticamente chaves DKIM e registros DNS durante a delegação de subdomínio. |
| **DMARC** | Autenticação de mensagens baseada em domínio, Relatórios e conformidade | Informa aos servidores receptores o que fazer se o SPF ou o DKIM falhar — e fornece relatórios sobre os resultados da autenticação. O DMARC tem três modos de política: nenhum, quarentena e rejeitar. |

### Modos de política do DMARC {#dmarc-policy-modes}

| Política | Ação | Quando usar |
| ------ | ------ | ----------- |
| `none` | Monitorar | O servidor de recebimento não faz nada se o DMARC falhar — mas ainda envia um relatório. Use isso ao delegar um subdomínio pela primeira vez para confirmar se a autenticação está funcionando sem correr o risco de perder a mensagem. |
| `quarantine` | Quarentena | O servidor de recebimento coloca mensagens com falha na pasta spam/lixo eletrônico. |
| `reject` | Rejeitar | O servidor de recebimento rejeita (devolve) mensagens com falha na autenticação. Modo estrito. Recomendado quando você está confiante na configuração da autenticação. |

### Configurar DMARC {#configure-dmarc}

O DMARC é configurado no momento da delegação de subdomínio, mas você também pode adicionar ou atualizar o DMARC para um subdomínio já delegado.

1. Na navegação à esquerda [!DNL Marketo Optimizer], expanda **[!UICONTROL Administração]** e selecione **[!UICONTROL Canais]**.

1. No painel, expanda **[!UICONTROL Configurações de email]** e selecione **[!UICONTROL Subdomínios]**.

1. Na lista Subdomínios, localize o subdomínio e verifique a coluna Registro do DMARC.

   Se um registro estiver ausente, um alerta será exibido.

1. Abra o subdomínio e role até a seção Registro do DMARC.

   * Se um registro DMARC já existir no domínio pai, [!DNL Marketo Optimizer] buscará os valores automaticamente. Você pode mantê-las ou substituí-las.
   * Se não existir nenhum registro, escolha **[!UICONTROL Gerenciar com o Adobe]** e o Adobe criará e hospedará o registro do DMARC.

1. Defina a política: `none`, `quarantine` ou `reject`. Comece com `none` a menos que você já tenha uma postura madura de DMARC em seu domínio pai.

1. (Opcional) Configure as marcas DMARC adicionais (`sp` para política de subdomínio, `pct` para porcentagem, `rua` e `ruf` para endereços de relatório).

1. Se estiver usando Totalmente Delegado, clique em **[!UICONTROL Salvar]**.

   O Adobe aplica o registro automaticamente. Se estiver usando CNAME, copie o registro DNS e peça à sua equipe de DNS para adicioná-lo e, em seguida, confirme-o no [!DNL Marketo Optimizer].

1. Aguarde até 48 horas para propagação DNS e verifique se o indicador de status do DMARC na página de subdomínio está verde/íntegro.

>[!TIP]
>
>Comece com `policy=none` para monitorar os relatórios de autenticação, depois avance para `quarantine` e, finalmente, para `reject` depois que seus relatórios mostrarem um alinhamento íntegro de SPF e DKIM. Mover diretamente para `reject` sem monitoramento pode fazer com que mensagens legítimas sejam rejeitadas.

## Pools de IP {#ip-pools}

Um pool de IPs é um grupo nomeado de endereços IP usados para enviar seu email. Os pools de IP são essenciais para a reputação do remetente: cada pool tem sua própria reputação com ISPs, portanto, um problema com um pool (por exemplo, um burst de marketing que aciona reclamações de spam) não contamina outro (por exemplo, confirmações transacionais).

### Tipos de pool {#pool-types}

| Tipo de pool | Disponibilidade | Descrição |
| --------- | ------------ | ----------- |
| **Pool de IPs compartilhados** | Disponível em Beta | Um pool de endereços IP gerenciados pela Adobe e compartilhados entre muitos clientes. A reputação é mantida pela Adobe em todo o pool. Melhor para volume de email baixo a médio e clientes que não desejam gerenciar o aumento gradual de IP. |
| **Pool de IPs dedicados** | Roteiro (GA) | Um ou mais endereços IP alocados exclusivamente à sua organização. Você é o dono da reputação. Recomendado para remetentes de alto volume. Inclui planejamento de aquecimento de IP e gerenciamento de registros PTR. |

### Revisar e atribuir um pool de IPs {#review-ip-pool}

Nesta versão, os pools de IP são pré-provisionados para sua organização. Atribua um pool de IP ao criar uma configuração de canal de email.

1. Na navegação à esquerda [!DNL Marketo Optimizer], expanda **[!UICONTROL Administração]** e selecione **[!UICONTROL Canais]**.
1. No painel, expanda **[!UICONTROL Configurações de email]** e selecione **[!UICONTROL pools de IP]**.
1. Confirme se um pool de IP com o status **[!UICONTROL Ativo]** está disponível para sua organização.
1. Passe o mouse sobre o pool para visualizar os endereços IP e seus registros PTR (DNS reverso).
1. Se sua organização tiver várias unidades de negócios ou marcas, planeje como você usará os pools de IP (por exemplo, pool de marketing versus pool de webinários) antes de criar as configurações de canal.

>[!IMPORTANT]
>
>Não misture tráfego de marketing e transacional no mesmo pool de IPs, mesmo quando o pool compartilhado estiver disponível. A configuração Tipo de email na configuração do canal (Marketing versus Transacional) controla o comportamento de supressão, mas as configurações de canal ainda devem usar pools distintos, quando possível.

<!--

### Frequently asked questions {#faq}

| Question | Answer |
| -------- | ------ |
| **Can I reuse the subdomain I already use in Marketo Engage?** | No. A subdomain can only be associated with one Adobe product at a time. Create a new subdomain (for example, mail2.contoso.com) for [!DNL Marketo Optimizer]. |
| **Why does my channel configuration show Failed?** | The most common reasons are: MX record validation failed (your subdomain DNS isn't fully configured); DMARC misalignment; or an IP pool that is in Processing and has never been associated with the selected subdomain. Open the configuration to see the specific reason. |
| **What happens if a personalization token has no value at send time?** | If you defined a fallback with the Handlebars `default` helper, the fallback is used. If not, the token resolves to an empty string. [!DNL Marketo Optimizer] warns you when a token has no fallback and the underlying attribute is not guaranteed by the audience definition. |
| **Can I personalize using account-level attributes?** | Not in this release. Personalization in [!DNL Marketo Optimizer] today supports profile attributes only. |
| **What's the maximum email size?** | 100 KB is the recommended best-practice cap for inbox rendering. [!DNL Marketo Optimizer] warns you in the editor if you exceed it. |
| **Can I migrate existing Marketo email templates into [!DNL Marketo Optimizer]?** | A guided self-serve migration tool — including Velocity-to-Handlebars conversion — is delivered at GA. In this release, you can manually rebuild templates or paste raw HTML. |
| **Will my updates to Marketo assets show up in [!DNL Marketo Optimizer]?** | No. Asset availability in [!DNL Marketo Optimizer] is based on a one-time copy from Marketo Design Studio. Re-uploaded or modified Marketo assets are not reflected in [!DNL Marketo Optimizer] today. Native asset upload and management within [!DNL Marketo Optimizer] is on the Beta roadmap. |

## Glossary {#glossary}

| Term | Definition |
| ---- | ---------- |
| **DKIM** | DomainKeys Identified Mail — cryptographic email signature. |
| **DMARC** | Domain-based Message Authentication, Reporting & Conformance. |
| **FBL** | Feedback Loop — a service ISPs offer to receive spam-complaint reports back to senders. |
| **Handlebars** | JavaScript templating language used in [!DNL Marketo Optimizer] for personalization expressions. |
| **IP pool** | Group of IP addresses used to send email. |
| **MX record** | Mail Exchange DNS record — directs incoming mail to the correct mail servers. |
| **NS record** | Name Server DNS record — used to delegate a subdomain. |
| **PTR record** | Pointer record — reverse DNS that maps an IP address back to a hostname. |
| **RBAC** | Role-Based Access Control. |
| **SPF** | Sender Policy Framework — DNS record listing authorized sending IPs. |
| **Subdomain delegation** | Granting Adobe authority over a portion of your domain (a subdomain) for sending email. |

-->


