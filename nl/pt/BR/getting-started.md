---
copyright:
  years: 1994, 2017, 2018, 2019
lastupdated: "2019-02-27"

keywords: compute order, Additional compute orders, Premium VLANs

subcollection: vlans

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}
{:important: .important}
{:note: .note}
{:DomainName: data-hd-keyref="DomainName"}

# Introdução às VLANs
{:#getting-started-with-vlans}

As redes locais virtuais (VLANs) são usadas pelo {{site.data.keyword.cloud}} para isolar o tráfego
de transmissão nas redes públicas e privadas. As VLANs são designadas conforme necessário para preencher outras ofertas. Por exemplo, se um pedido de cálculo for realizado para um data center no qual você ainda não tem uma presença, você receberá automaticamente uma VLAN. Pedidos de cálculo adicionais para o mesmo data center, que não especifiquem os requisitos de rede, geralmente são colocados na VLAN designada anteriormente. Todas as VLANs designadas automaticamente também serão removidas automaticamente quando seus recursos não precisarem mais delas.

As VLANs são específicas para os roteadores usados nos data centers do IBM Cloud, e um data center contém diversos roteadores para as redes públicas e privadas. Portanto, é possível que diversas VLANs sejam designadas em um único data center. Também é possível solicitar VLANs adicionais para construir topologias de rede mais complexas, normalmente com um [Dispositivo de Roteador Virtual](/docs/infrastructure/virtual-router-appliance?topic=virtual-router-appliance-getting-started-with-ibm-virtual-router-appliance).

As VLANs adquiridas são chamadas de **VLANs Premium** e as VLANs gerenciadas automaticamente pelo {{site.data.keyword.cloud}} são chamadas de **VLANs Automáticas**. Saiba mais sobre o funcionamento das VLANs em [Sobre as VLANs](/docs/infrastructure/vlans?topic=vlans-about-vlans).


## Gerenciando as VLANs
{:#managing-vlans}

Siga essas etapas para revisar as VLANs em sua conta.

  1. Abra o [console do IBM Cloud ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://{DomainName}/){: new_window} e efetue login em sua conta.
  2. No menu, selecione **Infraestrutura**.
  3. Na navegação do Portal do cliente, selecione **Rede > Gerenciamento de IP > VLANs**.

A listagem de VLANs exibe informações sobre suas VLANs e fornece acesso a cada VLAN, com os dispositivos ou sub-redes associados.

### Entendendo a seleção de pod vs. data center
{:#pod-vs-datacenter-selection}

As opções de onde solicitar uma VLAN atendem a necessidades e restrições diferentes. Essa seção resume os motivos pelos quais é possível selecionar uma opção em vez de outra.

A opção **Solicitar por Pod** permite que você especifique o pod exato (e, portanto, o roteador) no qual precisa de uma VLAN. Use essa opção se tiver um motivo específico para a VLAN existir nesse pod. Os motivos incluem o uso da VLAN com um Dispositivo de Gateway ou Firewall de diversas VLAN existente. Normalmente, ao solicitar VLANs adicionais como parte de um esquema de implementação maior, você sabe em qual pod deseja que as VLANs estejam. Em caso afirmativo, escolha essa opção.

Use a opção **Solicitar por Data Center** quando a localização da VLAN for menos importante. Essa opção é recomendável ao desejar definir um local como o valor inicial para o qual outros recursos serão agrupados. Se suas implementações seguirem uma primeira estratégia de rede (em vez de solicitar servidores primeiro), usar essa opção para estabelecer sua presença em um novo data center proporcionará a melhor experiência. Suas VLANs solicitadas são atendidas por qualquer pod no Data Center selecionado, portanto, não espere que um pod específico seja selecionado ao escolher essa opção.

É melhor usar a opção de localização menos específica disponível que atenda à sua necessidade atual.

### Pedidos complexos
{:#complex-orders-vlans}

A experiência de solicitação do portal permite solicitar somente uma única configuração de VLAN por pedido. Uma configuração consiste na rede, na opção de localização e na quantidade desejadas. Embora seja possível solicitar diversas configurações de VLAN em um único pedido por meio da API, cada quantidade de configuração é restrita a 1. Isso significa que cada configuração de VLAN fornecida é atendida de forma independente. Portanto, se cada configuração utilizar a opção de localização do data center, cada VLAN poderá ser designada a diferentes pods dentro desse data center.

### Uma nota sobre a capacidade
{:#note-about-capacity}

Uma tentativa de solicitação de VLAN pode ser evitada devido a restrições de capacidade no local selecionado. Se encontradas, essas restrições afetarão todos os usuários que tentarem solicitar VLANs nesse local, pois nenhum recurso estará disponível. Se possível, recomendamos estabelecer uma presença em outro data center e considerar a possibilidade de aproveitar [VLAN Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning). Se suas necessidades de localização forem flexíveis, recomendamos usar a opção de localização menos específica ao solicitar VLANs, pois isso permite maior flexibilidade na alocação de suas VLANs. Além disso, a capacidade de VLAN em um local que passou por uma tentativa anterior pode se tornar disponível posteriormente.


## Cancelando VLANs Premium
{:#canceling-premium-vlans}

Quando estiver pronto para remover uma VLAN premium, localize essa VLAN na listagem de VLANs de sua conta (consulte Gerenciando VLANs acima) e clique no ícone "X" na entrada para iniciar os prompts de cancelamento.

As VLANs Premium não podem ser canceladas se estiverem sendo usadas por outros produtos. Os seguintes usos evitam o cancelamento:

  * Servidores diretamente residentes na VLAN (em vez de truncados).
  * Sub-redes secundárias encaminhadas para a VLAN ou para um endereço IP na VLAN.
  * Produtos de firewall que atendem a toda a VLAN. Isso exclui firewalls de hardware não dedicados, por exemplo.
  * Associação a um Grupo de Ajuste Automático de Escala.
  * Truncamento para servidores (isso mudará no futuro).

Além disso, alguns produtos e recursos **não impedirão o cancelamento** de uma VLAN, mas serão afetados por sua remoção. São elas:

  * Sendo protegido por um Dispositivo de Roteador Virtual. A associação de VLAN será removida, independentemente de o bypass ter ou não sido efetuado.
