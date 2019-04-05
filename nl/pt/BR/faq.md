---
copyright:
  years: 1994, 2017, 2018, 2019
lastupdated: "2019-02-27"

keywords: new VLAN, subnet selector, VLAN moves

subcollection: vlans

---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:DomainName: data-hd-keyref="DomainName"}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}
{:generic: data-hd-programlang="generic"}
{:faq: data-hd-content-type='faq'}

# Perguntas Mais Freqüentes
{:#vlans-faqs}


## Posso mover um dispositivo existente para uma nova VLAN?
{: faq}

Os dispositivos existentes podem ser movidos para outras VLANs, mas apenas quando o movimento é solicitado. Como as VLANs são ligadas a um roteador e as conexões para cada roteador são dependentes do local físico do dispositivo, alguns movimentos de VLAN podem requerer uma realocação física também. Esse é sempre o caso quando a nova VLAN está localizada em um data center diferente, mas
também pode se aplicar ao mover um dispositivo para uma VLAN diferente dentro do mesmo data center. Fazer essa mudança interrompe a conectividade de rede e requer a mudança do endereço IP do dispositivo quando a conexão é movida para a nova VLAN. Ao mover um dispositivo para uma nova VLAN pedimos que o planejamento amplo seja permitido porque a máquina estará off-line durante a movimentação.


## Existe uma maneira de especificar na solicitação qual VLAN desejo usar em meu dispositivo?
{: faq}

Sim, uma VLAN específica pode ser selecionada durante o processo de realização de pedido. Ao pedir um dispositivo, essa opção estará disponível no final do formulário de pedido. Uma VLAN privada é selecionada, seguida por uma VLAN pública. Observe também que um seletor de sub-rede de seleção **opcional** é apresentado para cada VLAN. Apenas selecione uma sub-rede se tiver motivos para isso, pois a seleção de uma sub-rede que não tem endereços IP disponíveis afetará negativamente o cumprimento do dispositivo (Consulte as [Perguntas frequentes sobre a sub-rede](/docs/infrastructure/subnets?topic=subnets-subnets-faq) para obter mais detalhes).

É importante observar que a VLAN selecionada deve estar localizada no mesmo data center que o dispositivo. Não podemos designar um dispositivo para uma VLAN que esteja em um data center diferente.


## Quantos dispositivos podem ser designados para uma única VLAN?
{: faq}

Atualmente, não existe nenhum limite para o número de dispositivos associados a uma única VLAN a qualquer momento, no entanto, quando um firewall de hardware está associado a uma VLAN, o tipo do firewall pode impor restrições ao número de dispositivos que residem na VLAN.


## Que tipos de dispositivos são designados a uma VLAN?
{: faq}

Qualquer dispositivo que tenha uma conexão de rede será associado a uma VLAN. Os servidores dedicados têm uma conexão de rede pública e privada, portanto, você verá esses dispositivos associados a VLANs públicas e privadas.

## Como entroncar minhas VLANs em meus servidores?
{: faq}

As VLANs podem ser truncadas para servidores bare metal somente por meio do uso da API, pois nenhuma interface do portal está disponível para essa atividade. Para obter mais informações sobre o gerenciamento de VLANs como troncos, consulte os links da documentação da API abaixo.
* https://softlayer.github.io/reference/services/SoftLayer_Network_Component/addNetworkVlanTrunks
* https://softlayer.github.io/reference/services/SoftLayer_Network_Component/removeNetworkVlanTrunks

## O que significa quando, ao solicitar uma VLAN, sou informado de que não há nenhuma disponível?
{: faq}

Consulte [Uma nota sobre a capacidade](/docs/infrastructure/vlans?topic=vlans-getting-started-with-vlans#a-note-about-capacity).


## Por que os meus dispositivos não conseguem se comunicar uns com os outros na mesma VLAN privada?
{: faq}

Se cada servidor estiver em uma sub-rede diferente, por padrão, eles não poderão se comunicar por meio de endereços IP. Tecnicamente, seus servidores podem se comunicar usando os métodos da Camada 2 do Modelo OSI porque estão na mesma VLAN (uma construção da Camada 2). Para que a comunicação de protocolo da Internet (IP) (também chamada de Camada 3) funcione, é possível incluir uma rota para a sub-rede com a qual você está tentando se comunicar em cada servidor (a rota é diferente em cada servidor) ou ativar o [VLAN Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning). Observe que o [VLAN Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning) tem implicações adicionais, portanto, revise o recurso em detalhes antes de decidir ativá-lo.


## Quais são as opções se eu precisar que dispositivos em diferentes sub-redes privadas dentro da mesma VLAN se comuniquem por padrão, mas não desejar ativar VLAN Spanning?
{: faq}

Entendemos que o gerenciamento de rotas em servidores é complicado, considerando que o {{site.data.keyword.cloud}} designa e remove automaticamente as sub-redes primárias, conforme necessário. Também entendemos que a [VLAN Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning) nem sempre é uma possibilidade. Se tiver uma implementação grande que seja prejudicada por esse comportamento, somente será possível solicitar uma sub-rede primária de acomodação em uma [VLAN Premium](/docs/infrastructure/vlans?topic=vlans-about-vlans#premium-vlans). Os encargos serão aplicados a essa sub-rede e podem variar de acordo com a solicitação. Conceder ou negar tais solicitações com base em cada caso (não com base em cada conta, mas em cada solicitação) fica a nosso próprio critério. Siga essas instruções para solicitar uma sub-rede primária de tamanho especial:

  1. Abra o [console do IBM Cloud ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://{DomainName}/){: new_window} e efetue login em sua conta.
  1. No menu, selecione **Infraestrutura Clássica**. 
  1. No menu de navegação da Infraestrutura Clássica, selecione **Rede > Gerenciamento de IP > VLANs**.
  1. Se necessário, solicite uma VLAN Premium. Consulte [Solicitando VLANs Premium](/docs/infrastructure/vlans?topic=vlans-ordering-premium-vlans).
  1. Abra um chamado navegando até **Suporte > Incluir Chamado** no menu.
    - Assunto: "Pergunta sobre rede privada" ou "Pergunta sobre rede pública"
    - Título: "Solicitação de sub-rede primária grande"
    - Detalhes: especifique a VLAN Premium na qual deseja que a sub-rede seja ativada usando a notação datacenter.router.vlan (por exemplo, ams03.bcr01.1234). Em seguida, especifique o tamanho desejado para a sub-rede na notação CIDR (por exemplo, /25). Indique quantos servidores você planeja comprar e em qual período de tempo. Além disso, explique como seu uso seria prejudicado sem a sub-rede solicitada. Forneça uma explicação detalhada sobre como sua situação seria prejudicada, pois essas informações nos ajudam a avaliar melhorias em nossa plataforma. Nenhuma outra propriedade da sub-rede será considerada, portanto, não há necessidade de outras especificações.
