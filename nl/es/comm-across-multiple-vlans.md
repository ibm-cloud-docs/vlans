---
copyright:
  years: 1994, 2017
lastupdated: "2017-11-29"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Permitir a los servidores comunicarse mediante la red privada en varias VLAN

**Para conexiones cruzadas entre dos o más servidores.**

 * Nuestra red privada es de conexión cruzada. Su primera compra de servidor genera una VLAN privada para la cuenta con 64 IP privadas.
 * Todas sus futuras compras de servidores se colocarán en la misma VLAN para que sus servidores puedan comunicarse por la red privada.
 * Si espera tener más de 64 servidores, la VLAN crecerá automáticamente como sea necesario. No se necesita abrir una incidencia de soporte.
 * No siempre podemos garantizar que los servidores se coloquen en los mismos direccionadores, o si tiene servidores en varias ubicaciones, necesitará Habilitar la expansión de red privada mediante el portal.

Puede realizar esta tarea de configuración en el [Portal del cliente ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://control.softlayer.com/) seleccionando **Red -> Gestión de IP -> VLAN + Expandir (tabulador)**.

Se le llevará a la pantalla donde puede seleccionar **Sí** y, a continuación, seleccionar **Actualizar el valor de expansión de VLAN** para finalizar el proceso de configuración.
