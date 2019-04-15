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

# Acerca de las VLAN
{:#about-vlans}

Las VLAN son básicas para direccionar el tráfico hacia los recursos. Quizás nunca necesitará interaccionar directamente con ninguna VLAN, porque se gestionan automáticamente: se asignan cuando se necesitan y se eliminan cuando no se necesitan.

Una VLAN es un concepto de red. Permite crear dominios de difusión a nivel de [OSI Model ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://en.wikipedia.org/wiki/OSI_model) capa 2, la _capa
de enlace de datos_. Las VLAN proporcionan un método de identificación de paquetes y permiten que coexistan varias cargas de trabajo en el mismo equipamiento físico. Para obtener más información sobre VLAN, consulte [este artículo ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://en.wikipedia.org/wiki/Virtual_LAN).

## Tipos de VLAN
{:#types-of-vlans}

Hay dos tipos diferentes de VLAN, que {{site.data.keyword.cloud}} denomina **Automática** y **Premium**. Cada una tiene un rol distinto y es importante comprender las diferencias, según sus necesidades.

### VLAN automáticas
{:#automatic-vlans}

Las VLAN automáticas, {{site.data.keyword.cloud}} las gestiona automáticamente; se asignan y se eliminan según las necesidades para satisfacer las necesidades de otros productos que adquiera. Generalmente, tiene una VLAN automática por cada direccionador. Las VLAN automáticas se asocian a servidores que se han pedido sin seleccionar una VLAN específica. No se puede hacer pedidos ni cancelar las VLAN automáticas porque solo existen en su cuenta cuando nuestros sistemas determinan que son necesarias y se eliminan cuando nuestros sistemas determinan que ya no se necesitan.

### VLAN Premium
{:#about-premium-vlans}

Las VLAN Premium se adquieren al hacer un pedido de una VLAN. Consulte [Pedido de VLAN Premium](/docs/infrastructure/vlans?topic=vlans-ordering-premium-vlans) para obtener instrucciones. Las VLAN Premium permanecen en su cuenta hasta que se cancelan de forma explícita. Puede pedir tantas VLAN premium como desee, siempre sujeto a sus limitaciones de capacidad. Si se diera el caso de que no hay suficiente capacidad disponible, busque alguna VLAN en otro pod o centro de datos.

Una característica importante de las VLAN Premium es que no se seleccionan automáticamente para satisfacer un pedido de servidor. Las VLAN Premium se deben seleccionar explícitamente durante el proceso de pedido de servidor para que pueden tener servidores que residan en ellas. Consulte las [Preguntas más frecuentes (FAQ)](/docs/infrastructure/vlans?topic=vlans-vlans-faqs#is-there-a-way-to-specify-which-vlan-i-want-to-use-for-my-device-when-i-order-it-) para obtener instrucciones sobre la selección de VLAN.


## Identificación de VLAN
{:#vlan-identification}

Las VLAN existen en direccionadores dentro de los centros de datos de IBM Cloud. Cada VLAN está identificada por una combinación exclusiva de número, direccionador y ubicación de centro de datos. Por ejemplo la `VLAN 829` pública, que se ubica en el direccionador `fcr02` dentro del centro de datos `SJC01` se identifica como `sjc01.fcr02.829`. La VLAN 2234 privada, ubicada en el direccionador `bcr01` en el centro de datos `AMS01` se identifica como `ams01.bcr01.2234`.


## VLAN y subredes
{:#vlans-subnets}

Las VLAN pueden contener una o más subredes. Al igual que con las VLAN, se añaden o eliminan subredes automáticamente a medida que los dispositivos requieren direcciones IP. Encontrará detalles sobre las subredes que puede haber y cómo funcionan en [Subredes e IP](/docs/infrastructure/subnets?topic=subnets-getting-started-subnets-ips).


## Comunicación dentro de una VLAN
{:#communication-within-vlans}

Todos los recursos dentro de una VLAN pueden comunicarse, pero esto no significa que lo harán, de forma predeterminada. Es importante recordar que las VLAN son una construcción de OSI Model Capa 2 y que las subredes/IP son una construcción de Capa 3. La comunicación se realiza de forma distinta en cada capa. Los recursos que se encuentran en VLAN distintas, sea en la red pública o privada, no se pueden comunicar entre ellos por métodos de capa 2.

### Comunicación dentro de una VLAN en la red pública
{:#communication-within-vlans-public}

No hay restricciones inherentes para la comunicación entre recursos en la red pública, sea en una o varias VLAN dentro de la infraestructura de red pública de {{site.data.keyword.cloud}} o en internet. Se pueden añadir restricciones introduciendo un cortafuegos o un dispositivo de pasarela.

### Comunicación dentro de una VLAN en la red privada
{:#communication-within-vlans-private}

De forma predeterminada, solo se pueden comunicar las instancias de cálculo dentro de una misma subred, aunque haya varias subredes dentro de una misma VLAN. No obstante, es posible comunicarse con otras subredes de la misma VLAN siempre que las instancias de cálculo tengan entradas de ruta para las subredes adicionales de la VLAN. Gestionar las entradas de ruta en todos los nodos de cálculo que necesitan comunicarse a través de subredes privadas puede ser complicado. Para las situaciones en que se requiere comunicación predeterminada entre todas las instancias de cálculo dentro de una misma VLAN, consulte [Expansión de VLAN](/docs/infrastructure/vlans?topic=vlans-vlan-spanning). Tenga en cuenta que la expansión de VLAN tiene amplias implicaciones y se debe revisar cuidadosamente antes de habilitarla.
