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

# Preguntas frecuentes
{:#vlans-faqs}


## ¿Puedo mover un dispositivo existente a una nueva VLAN?
{: faq}

Los dispositivos existentes se pueden mover a otras VLAN, pero solo cuando se solicite el traslado. Dado que las VLAN están enlazadas a un direccionador y las conexiones a cada direccionador dependen de la ubicación física del dispositivo, algunos traslados de VLAN también pueden necesitar una reubicación física. Este siempre es el caso cuando la nueva VLAN se ubica en un centro de datos distinto, pero también se puede aplicar al mover un dispositivo a una VLAN distinta dentro del mismo centro de datos. Realizar este cambio interrumpe la conectividad de red y necesita cambiar la dirección IP del dispositivo cuando la conexión se mueve a la nueva VLAN. Al mover un dispositivo a una nueva VLAN, pedimos que se permita la planificación de ejemplo, ya que la máquina estará fuera de línea durante el tiempo del traslado.


## ¿Hay alguna forma de especificar qué VLAN deseo utilizar para mi dispositivo al pedirla?
{: faq}

Sí, se puede seleccionar una VLAN específica durante el proceso de pedido. Al hacer un pedido de un dispositivo, esta opción estará disponible al final del formulario de pedido. Se selecciona una VLAN privada, seguida por una VLAN pública. Observe también que para cada VLAN se presenta un selector de subred; esta selección es **opcional**. Seleccione una subred únicamente si tiene un motivo para hacerlo, ya que seleccionar una subred que no disponga de direcciones IP disponibles impactará negativamente en la ejecución del dispositivo (consulte [Preguntas más frecuentes (FAQ) de subred](/docs/infrastructure/subnets?topic=subnets-subnets-faq) para obtener más detalles).

Es importante tener en cuenta que la VLAN seleccionada se debe ubicar en el mismo centro de datos que el dispositivo. No podemos asignar un dispositivo a una VLAN que esté en un centro de datos distinto.


## ¿Cuántos dispositivos se pueden asignar a una única VLAN?
{: faq}

Actualmente no hay ningún límite en cuanto al número de dispositivos asociados con una única VLAN en cualquier momento; sin embargo, cuando un cortafuegos de hardware está asociado con una VLAN, el tipo de cortafuegos puede imponer restricciones en el número de dispositivos que residen en la VLAN.


## ¿Qué tipos de dispositivos se asignan a una VLAN?
{: faq}

Cualquier dispositivo que tenga una conexión de red se asignará con una VLAN. Los servidores dedicados tienen una conexión de red pública y privada, por lo que verá dichos dispositivos asociados con las VLAN públicas y privadas.

## ¿Cómo puedo establecer una relación troncal entre mis VLAN y mis servidores?
{: faq}

Las VLAN solo se pueden conectar a servidores nativos mediante API; no hay ninguna interfaz de portal disponible para esta actividad. 
Para obtener más información sobre cómo gestionar las VLAN como conexiones troncales, consulte los siguientes enlaces a la documentación de la API.
* https://softlayer.github.io/reference/services/SoftLayer_Network_Component/addNetworkVlanTrunks
* https://softlayer.github.io/reference/services/SoftLayer_Network_Component/removeNetworkVlanTrunks

## Al hacer un pedido de una, ¿qué significa si se me dice que no hay ninguna VLAN disponible?
{: faq}

Consulte [Una anotación sobre la capacidad](/docs/infrastructure/vlans?topic=vlans-getting-started-with-vlans#a-note-about-capacity).


## ¿Por qué mis dispositivos no se pueden comunicar entre ellos en la misma VLAN privada?
{: faq}

Si cada servidor se encuentra en una subred distinta, de forma predeterminada no podrán comunicarse mediante las direcciones IP. Técnicamente, sus servidores se pueden comunicar utilizando métodos de OSI Model Capa 2 porque se encuentran en la misma VLAN (una construcción de Capa 2). Para que funcione la comunicación con el Protocolo Internet (IP) (también denominado Capa 3), puede añadir una ruta a la subred con la que intenta comunicar en cada servidor (la ruta es distinta en cada servidor) o bien habilitar la [expansión de VLAN](/docs/infrastructure/vlans?topic=vlans-vlan-spanning). Tenga en cuenta que la [expansión de VLAN](/docs/infrastructure/vlans?topic=vlans-vlan-spanning) tiene implicaciones adicionales, por lo que debe consultar la información sobre característica en detalle antes de decidir habilitarla.


## ¿De qué opciones dispongo si necesito que los dispositivos de distintas subredes privadas dentro de la misma VLAN se comuniquen de forma predeterminada pero no quiero habilitar la expansión de VLAN?
{: faq}

Comprendemos que es complicado gestionar rutas en servidores teniendo en cuenta que {{site.data.keyword.cloud}} asigna y elimina subredes primarias automáticamente según las necesidades. También comprendemos que la [expansión de VLAN](/docs/infrastructure/vlans?topic=vlans-vlan-spanning) o es siempre posible. Si tiene un despliegue grande que se ve dificultado por este comportamiento, puede solicitar una subred primaria de alojamiento solo en una [VLAN Premium](/docs/infrastructure/vlans?topic=vlans-about-vlans#premium-vlans). Se aplicarán cargos a esta subred y pueden variar según la solicitud. Es decisión nuestra otorgar o denegar estas solicitudes caso por caso (no cuenta por cuenta, sino por cada solicitud). Siga estas instrucciones para solicitar una subred primaria de un tamaño especial:

  1. Abra la [consola de IBM Cloud ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://{DomainName}/){: new_window} e inicie sesión en su cuenta.
  1. En el menú, seleccione **Infraestructura clásica**. 
  1. En el menú de navegación de Infraestructura clásica, seleccione **Red > Gestión de IP > VLAN**.
  1. Pida una VLAN Premium, si la necesita. Consulte [Pedido de VLAN Premium](/docs/infrastructure/vlans?topic=vlans-ordering-premium-vlans).
  1. Abra un tíquet navegando a **Support > Añadir tíquet** en el menú.
    - Asunto: "Pregunta de red privada" o "Pregunta de red pública"
    - Título: "Solicitud de subred primaria grande"
    - Detalles: Especifique la VLAN Premium donde desea la subred utilizando la notación datacenter.router.vlan (por ejemplo, ams03.bcr01.1234). A, especifique el tamaño deseado de la subred en notación CIDR (por ejemplo, /25). Indique cuántos servidores tiene previsto adquirir y durante qué período de tiempo. Adicionalmente, explique cómo se verá dificultado su uso sin la subred que solicita. Dé explicaciones detalladas de cómo se vería dificultada su situación, porque esto nos ayuda a evaluar posibles mejoras en nuestra plataforma. No se tendrán en cuenta otras propiedades de la subred, por lo que no son necesarias más especificaciones.
