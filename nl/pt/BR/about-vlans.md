---
copyright:
  years: 1994, 2017, 2018, 2019
lastupdated: "2019-02-27"

keywords: VLANs, different role, network concept

subcollection: vlans

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:DomainName: data-hd-keyref="DomainName"}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}
{:generic: data-hd-programlang="generic"}

# Sobre as VLANs
{:#about-vlans}

As VLANs são essenciais para direcionar o tráfego para seus recursos. Pode nunca ser preciso interagir diretamente com nenhuma VLAN, porque elas são gerenciadas automaticamente, são designadas conforme necessário e são removidas quando não são mais necessárias.

Uma VLAN é um conceito de rede. Ela permite que você crie domínios de transmissão no nível da camada 2 do [Modelo OSI ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://en.wikipedia.org/wiki/OSI_model), a _camada de link de dados_. As VLANs fornecem um método de identificação de pacotes e permitem que diversas cargas de trabalho coexistam no mesmo equipamento físico. Para obter mais informações sobre as VLANs, consulte [esse artigo ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://en.wikipedia.org/wiki/Virtual_LAN).

## Tipos de VLANs
{:#types-of-vlans}

Há dois tipos distintos de VLANs, que são referenciadas pelo {{site.data.keyword.cloud}} como **Automática** e **Premium**. Cada uma delas desempenha uma função diferente e, dependendo de suas necessidades, é importante compreender suas diferenças.

### VLANs Automáticas
{:#automatic-vlans}

As VLANs Automáticas são gerenciadas pelo {{site.data.keyword.cloud}} automaticamente e são designadas e removidas conforme necessário para atender às necessidades de outros produtos solicitados. Normalmente, você tem uma VLAN automática por roteador. As VLANs Automáticas são associadas a servidores solicitados sem uma VLAN específica selecionada. Não é possível solicitar ou cancelar VLANs automáticas, pois elas existem em sua conta somente quando nossos sistemas determinam que são necessárias e são removidas quando nossos sistemas determinam o contrário.

### VLANs Premium
{:#about-premium-vlans}

As VLANs Premium são adquiridas por meio da solicitação de uma VLAN. Consulte [Solicitando VLANs Premium](/docs/infrastructure/vlans?topic=vlans-ordering-premium-vlans) para obter instruções. As VLANs Premium permanecem em sua conta até serem explicitamente canceladas. É possível solicitar quantas VLANs premium desejar, sujeito a limitações de capacidade. Caso a capacidade esteja indisponível, procure VLANs em outro pod ou data center.

Uma distinção importante das VLANs Premium é que elas não são selecionadas automaticamente para atender a uma necessidade do servidor. As VLANs Premium devem ser explicitamente selecionadas durante o processo de solicitação do servidor para que os servidores residam nelas. Consulte as [Perguntas frequentes](/docs/infrastructure/vlans?topic=vlans-vlans-faqs#is-there-a-way-to-specify-which-vlan-i-want-to-use-for-my-device-when-i-order-it-) para obter instruções sobre a seleção de VLANs.


## Identificação de VLAN
{:#vlan-identification}

As VLANs existem nos roteadores dos data centers do IBM Cloud. Cada VLAN é identificada por uma combinação exclusiva de número, roteador e local de data center. Por exemplo, a `VLAN 829` pública, localizada no roteador `fcr02` do data center `SJC01`, é identificada por `sjc01.fcr02.829`. A VLAN 2234 privada, localizada no roteador `bcr01` do data center `AMS01`, é identificada por `ams01.bcr01.2234`.


## VLANs e sub-redes
{:#vlans-subnets}

As VLANs podem conter uma ou mais sub-redes. Como as VLANs, algumas sub-redes são incluídas e removidas automaticamente, conforme os dispositivos requerem endereços IP. É possível ver detalhes sobre quais sub-redes podem existir e sua operação em [Sub-redes e IPs](/docs/infrastructure/subnets?topic=subnets-getting-started-subnets-ips).


## Comunicação em uma VLAN
{:#communication-within-vlans}

Todos os recursos em uma VLAN podem se comunicar, mas isso não significa que eles farão isso, por padrão. É importante lembrar que VLANs são uma construção da Camada 2 do Modelo OSI e que sub-redes/IPs são uma construção da Camada 3. A comunicação acontece de maneira diferente em cada camada. Recursos em VLANs diferentes, seja na rede pública ou privada, não podem se comunicar uns com os outros por meio dos métodos da camada 2.

### Comunicação em uma VLAN na rede pública
{:#communication-within-vlans-public}

Não há restrições inerentes à comunicação entre recursos na rede pública, seja em uma ou mais VLANs dentro da infraestrutura de rede pública do {{site.data.keyword.cloud}} ou na Internet. Restrições podem ser incluídas pela introdução de um Firewall ou Dispositivo de Gateway.

### Comunicação em uma VLAN na rede privada
{:#communication-within-vlans-private}

Por padrão, somente o cálculo na mesma sub-rede pode se comunicar, mesmo que diversas sub-redes estejam na mesma VLAN. No entanto, é possível se comunicar com outras sub-redes na mesma VLAN, desde que as instâncias de cálculo tenham entradas de rota para as sub-redes adicionais nessa VLAN. Gerenciar entradas de rota em todos os nós de cálculo que precisam se comunicar entre sub-redes privadas pode ser complicado. Para as situações nas quais a comunicação padrão é necessária entre todos os cálculos na mesma VLAN, consulte [VLAN Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning). Observe que VLAN Spanning tem implicações amplas e deve ser revisado cuidadosamente antes da ativação.
