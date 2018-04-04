---
copyright:
  years: 1994, 2017
lastupdated: "2017-10-17"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Preguntas frecuentes


## ¿Puedo mover un dispositivo existente a una nueva VLAN?

Los dispositivos existentes se pueden mover a otras VLAN, pero solo cuando se solicite el traslado. Dado que las VLAN están enlazadas a un direccionador y las conexiones a cada direccionador dependen de la ubicación física del dispositivo, algunos traslados de VLAN también pueden necesitar una reubicación física. Este siempre es el caso cuando la nueva VLAN se ubica en un centro de datos distinto, pero también se puede aplicar al mover un dispositivo a una VLAN distinta dentro del mismo centro de datos. Realizar este cambio interrumpe la conectividad de red y necesita cambiar la dirección IP del dispositivo cuando la conexión se mueve a la nueva VLAN. Al mover un dispositivo a una nueva VLAN, pedimos que se permita la planificación de ejemplo, ya que la máquina estará fuera de línea durante el tiempo del traslado.


## ¿Hay alguna forma de especificar qué VLAN deseo utilizar para mi dispositivo al pedirla?

Sí, se puede especificar una VLAN específica durante el proceso de pedido. Al pedir un dispositivo, esta opción estará disponible al final del formulario de pedido. Se selecciona una VLAN privada, seguida por una VLAN pública. Es importante tener en cuenta que la VLAN se debe ubicar en el mismo centro de datos que el dispositivo. No podemos asignar un dispositivo a una VLAN que esté en un centro de datos distinto.

## ¿Cuántos dispositivos se pueden asignar a una única VLAN?

En este momento no hay límite en el número de dispositivos asociados con una única VLAN en cualquier momento; sin embargo, cuando un cortafuegos de hardware está asociado con una VLAN, las reglas del cortafuegos pueden imponer restricciones en el número de dispositivos que residen en la VLAN.

## ¿Funcionan las VLAN en la red pública y privada?

Sí, hay VLAN públicas y privadas. En la mayoría de los casos, un dispositivo tiene una conexión pública y otra privada, lo que significa que tendrán una conexión en una VLAN pública y privada.

## ¿Qué tipos de dispositivos se asignan a una VLAN?

Cualquier dispositivo que tenga una conexión de red se asignará con una VLAN. Los servidores dedicados tienen una conexión de red pública y privada, por lo que verá dichos dispositivos asociados con las VLAN públicas y privadas (una VLAN por tipo de conexión, por dispositivo).

Los cortafuegos de hardware funcionan de una forma un poco distinta: se colocan frente a una VLAN para interceptar y filtrar tráfico. Estos dispositivos están enlazados a la VLAN para la que sirven, pero no residen en este momento en la propia VLAN.
