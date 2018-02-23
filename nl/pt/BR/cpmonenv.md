---

copyright:

  years: 1994, 2018

lastupdated: "2017-12-04"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}
{:screen: .screen}
{:new_window: target="_blank"}


# Monitorando seu ambiente e eventos do sistema
{: #customerportal_cpmonenvsysevent}

Monitorar seu ambiente significa que você tem a capacidade de verificar dispositivos a qualquer momento e que é notificado automaticamente se um de seus dispositivos fica inativo. Também é possível monitorar eventos do sistema para manter seus sistemas em execução sem problemas.  
{: shortdesc}

## Monitorando seu ambiente
{: #cpmonenv}

No mínimo, use monitoramento de ping básico, mas você pode customizar suas opções de monitoramento de uma maneira que se adeque melhor às suas necessidades de negócios.

### Ficando informado sobre manutenção de rede e eventos não planejados
{: #cp_stayinfomaintevent}

De vez em quando, a manutenção de rede planejada e emergencial é inevitável. A infraestrutura do {{site.data.keyword.BluSoftlayer_full}} mantém vários canais, como a [conta do Twitter ![Ícone de link externo](../icons/launch-glyph.svg)](https://twitter.com/softlayernotify){:new_window}, para mantê-lo informado sobre todos os eventos de manutenção planejados e emergenciais. Além disso, é possível [assinar notificações por e-mail](/docs/customer-portal/cpsub2not.html){:new_window} do Sistema de Gerenciamento de Eventos. Esse serviço complementar envia e-mails automaticamente aos usuários inscritos sobre eventos não planejados que possam impactar os serviços.

### Usando a infraestrutura móvel do {{site.data.keyword.BluSoftlayer_notm}}
{: #cp_bmxinframobile}

Use a infraestrutura móvel do [{{site.data.keyword.BluSoftlayer_notm}} ![Ícone de link externo](../icons/launch-glyph.svg)](https://knowledgelayer.softlayer.com/topic/mobile-devices){:new_window} para gerenciar seus dispositivos de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}} em movimento usando seu dispositivo móvel iOS ou Android. A funcionalidade dentro da infraestrutura móvel do {{site.data.keyword.BluSoftlayer_notm}} inclui suporte de chamados, controle de dispositivo básico e monitoramento de largura da banda.

## Monitorando eventos do sistema
{: #customerportal_monevent}

É possível monitorar eventos do sistema visualizando logs de auditoria e logs de acesso.

### Visualizando um log de auditoria para uma conta
{: #cp_viewacctauditlog}

Cada conta do portal do cliente vem com um log de auditoria que rastreia as interações de cada usuário dentro do portal do cliente. Interações rastreadas incluem tentativas de login (sucesso e falhas), atualizações de velocidade da porta, ligar ou desligar e reinicializar, além daquelas interações feitas pela equipe de suporte de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}. Use as etapas a seguir para visualizar um log de auditoria para uma conta do usuário.

1. Acesse o [Portal do cliente ![Ícone de link externo](../icons/launch-glyph.svg)](https://control.softlayer.com/){:new_window} usando as suas credenciais exclusivas.
2. Selecione **Conta** > **Gerenciar** > **Log de auditoria** na barra de navegação para acessar o log de auditoria.

O log de auditoria inicialmente exibe as últimas 25 interações tomadas por usuários na conta. É possível visualizar até 200 interações a qualquer momento. Atualize o número de resultados mostrados na lista suspensa **Exibir**. Se as configurações mudaram, a coluna **Ação** para a interação conterá um link. Clique em qualquer link para visualizar a configuração impactada pela ação e detalhes sobre a mudança. Clicar no nome de dispositivo ou nome do usuário para qualquer interação redireciona você para a tela de detalhes do dispositivo ou a tela de perfil do usuário, respectivamente.

### Visualizando logs de acesso de um usuário
{: #cp_viewuserlogs}

Logs de acesso exibem dados para cada tentativa de acesso feita por um usuário do portal do cliente específico. Os logs exibem um registro de data e hora e o endereço IP para cada tentativa de acesso. Use as etapas a seguir para visualizar Logs de acesso de um usuário.

1. Acesse o [portal do cliente ![Ícone de link externo](../icons/launch-glyph.svg)](https://control.softlayer.com/){:new_window} usando as suas credenciais exclusivas.
2. Selecione **Conta** > **Usuários** na barra de menus para acessar a janela Usuários.
3. Na lista suspensa **Ações**, selecione **Visualizar log de auditoria** para visualizar o log de acesso do usuário.

O log de acesso para cada usuário exibe as tentativas de acesso feitas por esse usuário por data, juntamente com o endereço IP do qual a tentativa de acesso foi feita. Informações dentro do log de acesso são somente leitura; portanto, as edições para o conteúdo não podem ser feitas a qualquer momento. É possível visualizar os logs de acesso novamente a qualquer momento repetindo as etapas anteriores. Para sair dos logs e retornar à tela Usuários, clique no link **Visualizar todos os usuários** na parte superior da tela.