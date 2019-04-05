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

# Cómo empezar con las VLAN
{:#getting-started-with-vlans}

Las redes de área local virtual (VLAN) son utilizadas por {{site.data.keyword.cloud}} para aislar el tráfico de difusión en las redes públicas y privadas. Las VLAN se asignan a medida que se necesitan para dar servicio a otras ofertas. Por ejemplo, si hace un pedido de cálculo en un centro de datos donde todavía no tiene presencia, recibe automáticamente una VLAN. Los pedidos de cálculo adicionales al mismo centro de datos, que no especifiquen requisitos de red. se colocan generalmente en la VLAN asignada previamente. Todas las VLAN que se asignan automáticamente, se eliminan también automáticamente cuando sus recursos ya no las necesitan.

Las VLAN son específicas para los direccionadores utilizados en los centros de datos de IBM Cloud, y un centro de datos contiene varios direccionadores, tanto para redes públicas como privadas. Por lo tanto, es posible que se asignen varias VLAN dentro de un mismo centro de datos. También es posible pedir VLAN adicionales para construir topologías de red más complejas; generalmente en conjunción con
un [Virtual Router Appliance (dispositivo de direccionador virtual)](/docs/infrastructure/virtual-router-appliance?topic=virtual-router-appliance-getting-started-with-ibm-virtual-router-appliance).

Utilizamos los términos **VLAN Premium** para referirnos a las VLAN compradas y **VLAN automáticas** para las VLAN gestionadas automáticamente por {{site.data.keyword.cloud}}. Puede obtener más información sobre cómo funcionan las VLAN en [Acerca de las VLAN](/docs/infrastructure/vlans?topic=vlans-about-vlans).


## Gestión de VLAN
{:#managing-vlans}

Siga estos pasos para revisar las VLAN por su cuenta.

  1. Abra la [consola de IBM Cloud ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://{DomainName}/){: new_window} e inicie sesión en su cuenta.
  2. En el menú, seleccione **Infraestructura**.
  3. En la navegación del Portal de clientes, seleccione **Red > Gestión de IP > VLAN**.

La lista de las VLAN muestra información sobre las VLAN, y proporciona acceso a cada VLAN, junto con dispositivos o subredes que tenga asociados.

### Comprender la selección de pod frente a centro de datos
{:#pod-vs-datacenter-selection}

Las opciones sobre dónde hacer un pedido de una VLAN ofrecen distintas necesidades y restricciones. En esta sección se resumen los motivos por los que seleccionar una u otra opción.

La opción **Pedir por Pod** le permite especificar el pod exacto (y, por tanto, el direccionador) donde necesita una VLAN. Utilice esta opción si tiene un motivo concreto para que la VLAN esté en ese pod. Los motivos pueden ser utilizar la VLAN con un dispositivo de pasarela existente o un cortafuegos multiVLAN. Generalmente, si pide VLAN adicionales como parte de un mayor esquema de despliegue, sabe en qué pod quiere las VLAN. Si es así, elija esta opción.

Utilice la opción **Pedir por centro de datos** cuando la ubicación de la VLAN no sea tan importante. Esta es una mejor opción cuando desea inicializar una ubicación en la cual pondrá otros recursos en clúster. Si su despliegue sigue una estrategia de red primero (en lugar de pedir los servidores primero), es mejor utilizar esta opción para establecer su presencia en un nuevo centro de datos. Las VLAN solicitadas las crea cualquier pod del centro de datos seleccionado; no espere poder decidir el pod que se va a seleccionar al elegir esta opción.

Es mejor utilizar la opción de ubicación menos específica que se ajuste a su necesidad actual.

### Pedidos complejos
{:#complex-orders-vlans}

El pedido por portal sólo permite pedir una configuración de VLAN por pedido. Una configuración consiste indicar la opción deseada de red, de opción de ubicación y de cantidad. Aunque es posible pedir varias configuraciones de VLAN en un solo pedido mediante la API, la cantidad está restringida a 1. Esto significa que cada configuración de VLAN proporcionada se crea independientemente. Así pues, si cada configuración utiliza la opción de ubicación de centro de datos, cada VLAN se puede asignar a distintos pods dentro del centro de datos.

### Una anotación sobre la capacidad
{:#note-about-capacity}

Es posible que se impida un intento de hacer un pedido de una VLAN debido a restricciones de capacidad en la ubicación seleccionada. Si esto ocurre, afecta a todos los usuarios que intentan hacer pedidos de VLAN en esa ubicación, no hay ningún recurso disponible. Si es posible, le recomendamos establecer presencia en otro centro de datos y considerar la posibilidad de utilizar la [expansión de VLAN](/docs/infrastructure/vlans?topic=vlans-vlan-spanning). Si las necesidades de su ubicación son flexibles, es mejor utilizar la opción de ubicación menos específica al hacer pedidos de VLAN, porque esto permite una mayor flexibilidad al asignar las VLAN. Además, la capacidad de una VLAN en una ubicación que se ha intentado anteriormente, puede quedar disponible más tarde.


## Cancelación de VLAN Premium
{:#canceling-premium-vlans}

Cuando esté listo para eliminar una VLAN premium, localice la VLAN en la lista de VLAN de su cuenta (Consulte Gestión de las VLAN más arriba) y pulse en el icono "X" en la entrada para iniciar el proceso de cancelación.

NO se pueden cancelar las VLAN Premium si están siendo utilizadas por otros productos. Los usos siguientes impiden la cancelación:

  * Servidores directamente alojados en la VLAN (en lugar de conectados).
  * Subredes secundarias direccionadas a la VLAN o una dirección IP en la VLAN.
  * Productos de cortafuegos que den servicio a toda la VLAN. Esto excluye, por ejemplo, los cortafuegos de hardware no dedicados.
  * Asociación a un grupo de escalado automático.
  * Estar conectadas a servidores (esto cambiará en el futuro).

Adicionalmente, algunos productos y características **no impedirán la cancelación** de una VLAN, pero se verán afectados por su eliminación. Son los siguientes:

  * Estar protegido por un dispositivo de direccionador virtual (Virtual Router Appliance). La asociación de VLAN se eliminará, tanto si se está omitida como si no.
