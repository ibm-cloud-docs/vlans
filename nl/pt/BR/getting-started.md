---
copyright:
  years: 1994, 2017
lastupdated: "2017-10-20"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Introdução às VLANs

Uma VLAN é uma rede local virtual que pode ser criada para permitir aos clientes separar partes de uma rede maior em sub-redes menores. Uma VLAN funciona como um contêiner no qual as conexões e os endereços IPs de um único cliente podem permanecer separados de qualquer outro cliente. VLANs permitem melhor segurança e isolamento de certos problemas. 
Em nossa rede {{site.data.keyword.BluSoftlayer_notm}}, as VLANs fornecem a capacidade de particionar seus dispositivos e sub-redes. 

Você pode gerenciar suas VLANs na tela VLANs:

1. Em seu navegador, abra o [Portal do cliente ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://control.softlayer.com/){: new_window} e efetue login em sua conta.
2. Na navegação do Portal do cliente, selecione **Rede > Gerenciamento de IP > VLANs**.

A tela VLANs exibe informações sobre suas VLANs e fornece acesso a cada VLAN, juntamente com dispositivos ou sub-redes associados. Como um serviço incluído, os clientes podem ativar a Ampliação de VLAN, que conecta todas as VLANs de rede privada em uma conta permitindo, assim, que dispositivos em VLANs separadas se comuniquem uns com os outros. 

## Identificação de VLAN

VLANs existem em roteadores dentro de nossos data centers. Cada VLAN é identificada por um número exclusivo, roteador e local de data center. Por exemplo, a `VLAN 829`, que está localizada no roteador `fcr02` dentro do data center `SJC01` é identificada por nossos sistemas como `829 fcr02.sjc01`.

## Ampliação de VLAN

A ampliação de VLAN é uma configuração de conta que permite ao tráfego viajar entre VLANs privadas que pertencem a uma única conta. Devido à natureza da rede privada, muito pouco tráfego é permitido nas VLAN privadas de uma conta. Em geral, as VLANs protegem os dispositivos do tráfego de rede em outras contas do cliente. VLANs privadas levam essa proteção um passo adiante ao restringir o tráfego na VLAN para que ele ocorra apenas entre os dispositivos nessa VLAN; portanto, por padrão, os dispositivos que estão localizados em duas VLANs privadas diferentes não podem enviar tráfego uns para os outros. Ao [ativar a ampliação de VLAN](vlan-spanning.html), essa restrição é aumentada para que os dispositivos nas VLANs privadas diferentes de uma conta possam se comunicar.

### Quando devo ativar a ampliação da VLAN para a minha conta?

A ampliação de VLAN deve ser ativada quando a necessidade de negócios surgir. Por exemplo, se os servidores que residem em mais de uma sub-rede privada precisarem se comunicar, a ampliação de VLAN deve ser ativada. A comunicação entre VLANs não é específica para o local físico da VLAN; por exemplo, VLANs privadas no mesmo data center ainda são completamente segregadas entre si. 
Quando os dispositivos estão localizados em duas ou mais VLANs, cada uma delas com sua própria sub-rede, a ampliação de VLAN deve ser ativada para que os dispositivos se comuniquem.
