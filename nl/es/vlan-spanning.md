---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-27"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Habilitar o inhabilitar la expansión de VLAN

A veces, pueden existir varias VLAN de red privada en una única cuenta de cliente. Sin embargo, los dispositivos de red no pueden comunicarse entre sí en la red privada si no existen en la misma VLAN. La expansión de VLAN permite a todos los dispositivos de una cuenta comunicarse entre sí mediante la red privada, independientemente de su VLAN asignada. 

El servicio de expansión de VLAN se aplica a todos los dispositivos de la cuenta; la expansión podría no aplicarse a VLAN o a dispositivos específicos. La expansión de VLAN puede estar habilitada o inhabilitada según sea necesario, y lleva aproximadamente 15 minutos en procesarse, una vez que se haya realizado un cambio en el valor. Siga los pasos que se proporcionan en este artículo para habilitar o inhabilitar la expansión de VLAN en una cuenta.


1. Desde el navegador, abra el [Portal del cliente ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://control.softlayer.com/){: new_window} e inicie sesión en su cuenta.
2. En la navegación del Portal del cliente, seleccione **Red > Gestión de IP > VLAN**.
3. Seleccione el separador **Expandir** para acceder a la sección Expansión de VLAN.
4. Seleccione el botón de selección **Encendido** para habilitar la expansión de VLAN. Seleccione el botón de selección **Apagado** para inhabilitar la expansión de VLAN.

## Qué sucede a continuación

Tras actualizar las selecciones de expansión de VLAN, la solicitud puede tardar hasta 15 minutos en procesarse. Aparecerá una confirmación del cambio debajo del separador Expandir. Si habilita la expansión de VLAN, los dispositivos podrán comunicarse entre sí entre las VLAN utilizando la red privada. Si inhabilita la expansión, los dispositivos podrán conectarse entre sí solo si residen en la misma VLAN; la comunicación entre las VLAN ya no está habilitada. Los valores de expansión de VLAN se pueden actualizar en cualquier momento repitiendo los pasos que se proporcionan en este artículo. **Nota:** La conmutación entre los valores de expansión de VLAN en un pequeño espacio de tiempo puede dar lugar a un retraso en los valores que se aplican.
