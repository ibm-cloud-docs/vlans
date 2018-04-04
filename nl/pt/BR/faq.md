---
copyright:
  years: 1994, 2017
lastupdated: "2017-10-17"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Perguntas Mais Freqüentes


## Posso mover um dispositivo existente para uma nova VLAN?

Os dispositivos existentes podem ser movidos para outras VLANs, mas apenas quando o movimento é solicitado. Como as VLANs são ligadas a um roteador e as conexões para cada roteador são dependentes do local físico do dispositivo, alguns movimentos de VLAN podem requerer uma realocação física também. Esse é sempre o caso quando a nova VLAN está localizada em um data center diferente, mas
também pode se aplicar ao mover um dispositivo para uma VLAN diferente dentro do mesmo data center. Fazer essa mudança interrompe a conectividade de rede e requer a mudança do endereço IP do dispositivo quando a conexão é movida para a nova VLAN. Ao mover um dispositivo para uma nova VLAN pedimos que o planejamento amplo seja permitido porque a máquina estará off-line durante a movimentação.


## Existe uma maneira de especificar na solicitação qual VLAN desejo usar em meu dispositivo?

Sim, uma VLAN específica pode ser especificada durante o processo de pedido. Ao pedir um dispositivo, essa opção estará disponível no final do formulário de pedido. Uma VLAN privada é selecionada, seguida por uma VLAN pública. É importante observar que a VLAN deve estar localizada no mesmo data center que o dispositivo. Não podemos designar um dispositivo para uma VLAN que esteja em um data center diferente.

## Quantos dispositivos podem ser designados para uma única VLAN?

Atualmente não há limite para o número de dispositivos associados a uma única VLAN em qualquer momento; no entanto, quando um firewall de hardware está associado a uma VLAN, as regras de firewall podem impor restrições sobre o número de dispositivos que residem na VLAN.

## As VLANs funcionam na rede pública e na rede privada?

Sim, há VLANs públicas e privadas. Na maioria dos casos, um dispositivo tem uma conexão pública e uma conexão privada, o que significa que ele terá uma conexão em uma VLAN pública e em uma privada.

## Que tipos de dispositivos são designados a uma VLAN?

Qualquer dispositivo que tenha uma conexão de rede será associado a uma VLAN. Os servidores dedicados têm uma conexão de rede pública e uma privada, assim, você verá esses dispositivos associados com as VLANs públicas e privadas (uma VLAN por tipo de conexão, por dispositivo).

Os firewalls de hardware funcionam um pouco diferente: eles são posicionados na frente de uma VLAN para interceptar e filtrar o tráfego.
Esses dispositivos são ligados à VLAN à qual servem, mas eles não residem, de fato, na própria VLAN.
