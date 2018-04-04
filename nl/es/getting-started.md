---
copyright:
  years: 1994, 2017
lastupdated: "2017-10-20"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Cómo empezar con las VLAN

Una VLAN es una Red de área local virtual, que se puede crear para permitir a los clientes separar partes de una red más grande en subredes más pequeñas. Una VLAN funciona como un contenedor dentro de la cual pueden permanecer separados de cualquier otro cliente las conexiones del cliente único y las direcciones IP. Las VLAN permiten una mejor seguridad y el aislamiento de determinados problemas. En nuestra red de {{site.data.keyword.BluSoftlayer_notm}}, las VLAN proporcionan la capacidad de particionar los dispositivos y las subredes. 

Puede gestionar las VLAN desde la pantalla de las VLAN:

1. Desde el navegador, abra el [Portal del cliente ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://control.softlayer.com/){: new_window} e inicie sesión en su cuenta.
2. En la navegación del Portal del cliente, seleccione **Red > Gestión de IP > VLAN**.

La pantalla de las VLAN muestra información sobre las VLAN, y proporciona acceso a cada VLAN, junto con dispositivos o subredes asociados. Como un servicio añadido, los clientes pueden habilitar la Expansión de VLAN, que conecta todas las VLAN de red privada en una cuenta, permitiendo así a los dispositivos de VLAN independientes comunicarse entre sí. 

## Identificación de VLAN

Las VLAN existen en direccionadores dentro de nuestros centros de datos. Cada VLAN está identificada por un número exclusivo, un direccionador y una ubicación de centro de datos. Por ejemplo, `VLAN 829`, que se ubica en el direccionador `fcr02` dentro del centro de datos `SJC01`, está identificado por nuestros sistemas como `829 fcr02.sjc01`.

## Expansión de VLAN

La expansión de VLAN es un valor de cuenta que permite al tráfico viajar entre VLAN privadas que pertenecen a una cuenta única. Debido a la naturaleza de la red privada, se permite muy poco tráfico en las VLAN privadas de una cuenta. En general, las VLAN protegen a los dispositivos del tráfico de red en otras cuentas de cliente. Las VLAN privadas toman esta protección un paso más allá al restringir que el tráfico de la VLAN solo tenga lugar entre dispositivos de dicha VLAN; por lo tanto, de forma predeterminada, los dispositivos que están ubicados en dos VLAN privadas distintas podrían no enviarse tráfico entre sí. Al [habilitar la expansión de VLAN](vlan-spanning.html), esta restricción se elimina para que los dispositivos de VLAN privadas distintas de una cuenta puedan comunicarse.

### ¿Cuándo debería habilitar la expansión de VLAN para mi cuenta?

La expansión de VLAN debería habilitarse siempre que surja la necesidad empresarial. Por ejemplo, si los servidores que residen en más de una subred privada necesitan comunicarse, debería habilitarse la expansión de VLAN. La comunicación entre VLAN no es específica de la ubicación física de la VLAN; por ejemplo, las VLAN privadas del mismo centro de datos siguen estando completamente segregadas entre sí. Cuando los dispositivos están ubicados en dos o más VLAN, cada una con su propia subred, debe habilitarse la expansión de VLAN para que los dispositivos se comuniquen.
