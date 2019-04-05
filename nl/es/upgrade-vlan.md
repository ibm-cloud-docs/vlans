---
copyright:
  years: 1994, 2018, 2019
lastupdated: "2019-02-27"

keywords: Automatic VLAN, capabilities of a Premium VLAN, upgrade shortcut interface

subcollection: vlans

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Actualización de una VLAN automática
{:#upgrading-automatic-vlan}

Si ha creado una solución alrededor de una VLAN automática y después decide que desea que tenga las funciones de una VLAN Premium, puede actualizarla. La actualización no es reversible. La VLAN pasa a ser una VLAN Premium y permanece en su cuenta hasta que se cancela, momento en que se reclamará.

No siempre es posible actualizar las VLAN. Aún se aplican limitaciones en las capacidades de la VLAN.

De momento, la actualización solo en posible mediante la API. Hay dos métodos disponibles para hacerlo:

  1. Realice un pedido utilizando `SoftLayer_Product_Order.placeOrder`.
  2. Utilice la interfaz de acceso directo `SoftLayer_Network_Vlan.upgrade`.

## Formalización de un pedido
{:#place-vlan-order}

  1. Cree un pedido similar al de una VLAN Premium típica; específicamente, con el paquete y el precio correctos.
  1. Elimine las propiedades `location` y `routerId` que son obligatorias al hacer un pedido de una nueva VLAN Premium.
  1. Añada la propiedad `id` y rellénela con el valor de `SoftLayer_Network_Vlan.id` de la VLAN a actualizar.

## Interfaz de acceso directo
{:#vlan-shortcut-interface}

Ejecute la operación [SoftLayer_Network_Vlan.upgrade](https://softlayer.github.io/reference/services/SoftLayer_Network_Vlan/upgrade/) contra una VLAN existente inicializando la llamada con el valor de `SoftLayer_Network_Vlan.id` de la VLAN a actualizar. Esto encuentra la información adecuada de paquete y precio de la VLAN y hace el pedido necesario para realizar la de actualización. Con este método, los pedidos de actualización de VLAN sólo se realizarán si su cuenta cumple los requisitos para la aprobación automática de pedidos.

Consulte la documentación de la API de [SoftLayer_Network_Vlan.upgrade](https://softlayer.github.io/reference/services/SoftLayer_Network_Vlan/upgrade/) para obtener más detalles.

## ¿Qué sucede a continuación?
{:#upgrade-vlan-what-happens-next}

La VLAN cambia a VLAN Premium poco después de que se haya realizado el pedido de forma satisfactoria.
