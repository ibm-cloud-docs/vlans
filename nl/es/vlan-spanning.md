---

copyright:
  years: 1994, 2017, 2018, 2019
lastupdated: "2019-02-28"

keywords: VLAN Spanning VLAN, Default values, VLAN Spanning

subcollection: vlans

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:DomainName: data-hd-keyref="DomainName"}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}
{:generic: data-hd-programlang="generic"}


# Expansión de VLAN
{: #vlan-spanning}

La expansión de VLAN permite a todos los dispositivos de una cuenta comunicarse entre sí mediante la red privada, independientemente de la VLAN asignada a los dispositivos.
{: #shortdesc}

## Comprensión de la expansión de VLAN
{: #understanding-vlan-spanning}


En {{site.data.keyword.Bluemix}}, se puede utilizar la expansión de VLAN para muchos propósitos distintos y tiene un impacto en la comunicación de dispositivos. Para obtener más información sobre los aspectos básicos de la expansión de VLAN antes de empezar, consulte la información siguiente.
{: shortdesc}

### Cómo funciona la expansión de VLAN
{: #how-vlan-spanning-works}

Al habilitar la expansión de VLAN, todo el tráfico direccionado puede viajar entre todas las subredes privadas, a través de todas las VLAN privadas de su cuenta. Esto presta servicio a las necesidades de negocio que requieren una comunicación global del tráfico direccionado. Por ejemplo: Habilite la expansión de VLAN si los dispositivos que residen en más de una subred privada necesitan comunicarse, sea dentro de la misma VLAN o en distintas VLAN.

Cuando se habilita la expansión, afecta a toda la cuenta. No puede eximir a ninguna subred, VLAN o dispositivo de la expansión de VLAN. Si actualmente depende únicamente de subredes privadas para segregar servidores en roles o niveles, el hecho de habilitar la expansión de VLAN elimina esta segregación.
{:note}

### Valores predeterminados
{: #vlan-spanning-default-values}

De forma predeterminada, la expansión de VLAN está inhabilitada. Los dispositivos ubicados en dos subredes privadas distintas, sea en la misma VLAN o en VLAN distintas, no podrán enviarse tráfico de IP entre ellos.

### Servicios que habitualmente requieren expansión de VLAN
{: #vlan-spanning-services}

Hay guías de aprendizaje específicas disponibles para ayudarle a configurar la expansión de VLAN en su situación. Consulte los enlaces a [Otros recursos](/docs/infrastructure/vlans?topic=vlans-other-resources-vlan-spanning).


## Gestión de la expansión de VLAN
{: #manage-vlan-spanning}

Puede habilitar o inhabilitar la expansión de VLAN de su cuenta.
{: shortdesc}

Para actualizar la configuración de su cuenta, siga estos pasos:

  1. Desde el navegador, abra la consola de [{{site.data.keyword.Bluemix_notm}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://{DomainName}/){: new_window} e inicie sesión en su cuenta.
  2. En el menú, seleccione **Infraestructura**. Se abrirá el Portal de clientes.
  3. En la navegación del Portal de clientes, seleccione **Red > Gestión de IP > VLAN**.
  4. Seleccione el separador **Expandir** para acceder a la sección Expansión de VLAN.
  5. Seleccione el botón de selección **Activado** o **Desactivado** para habilitar o inhabilitar la expansión de VLAN según desee.

Si se conmuta la expansión de VLAN en un breve espacio de tiempo puede resultar en retrasos en la aplicación.
{:note}

La solicitud de actualización puede tardar hasta 15 minutos en procesarse. En la pantalla se visualiza la confirmación del cambio. Puede actualizar los valores de expansión de VLAN en cualquier momento repitiendo los pasos anteriores.
