---
copyright:
  years: 1994, 2018, 2019
lastupdated: "2019-02-27"

keywords: Automatic VLAN, capabilities of a Premium VLAN, upgrade shortcut interface

subcollection: vlans

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Fazendo upgrade de uma VLAN Automática
{:#upgrading-automatic-vlan}

Se você criou uma solução com base em uma VLAN Automática e decidir posteriormente que deseja que ela tenha os recursos de uma VLAN Premium, será possível fazer seu upgrade. O upgrade não é reversível. A VLAN se tornará uma VLAN Premium e permanecerá em sua conta até ser cancelada, quando será recuperada.

O upgrade das VLANs nem sempre é possível. As limitações de capacidade das VLANs ainda se aplicam.

No momento, o upgrade está disponível somente por meio da API. Há dois métodos disponíveis para isso:

  1. Realize um pedido usando o `SoftLayer_Product_Order.placeOrder`.
  2. Utilize a interface de atalho do `SoftLayer_Network_Vlan.upgrade`.

## Realizando um pedido
{:#place-vlan-order}

  1. Crie um pedido semelhante a uma VLAN Premium comum, especificamente com o pacote e a precificação corretos.
  1. Remova as propriedades `location` e `routerId` necessárias ao solicitar uma nova VLAN Premium.
  1. Inclua a propriedade `id` e preencha-a com o valor `SoftLayer_Network_Vlan.id` da VLAN que passará pelo upgrade.

## Interface de atalho
{:#vlan-shortcut-interface}

Execute a operação [SoftLayer_Network_Vlan.upgrade](https://softlayer.github.io/reference/services/SoftLayer_Network_Vlan/upgrade/) com relação a uma VLAN existente inicializando a chamada com o valor `SoftLayer_Network_Vlan.id` da VLAN que passará pelo upgrade. Com isso, é possível localizar as informações apropriadas de pacote e precificação para a VLAN e realizar o pedido necessário para executar o upgrade. Usando esse método, os pedidos de upgrade de VLAN serão realizados somente se sua conta se qualificar para a aprovação automática de pedidos.

Consulte a documentação da API para o [SoftLayer_Network_Vlan.upgrade](https://softlayer.github.io/reference/services/SoftLayer_Network_Vlan/upgrade/) para obter mais detalhes.

## O que acontece a seguir?
{:#upgrade-vlan-what-happens-next}

A VLAN é transformada em uma VLAN Premium logo após a realização bem-sucedida de um pedido.
