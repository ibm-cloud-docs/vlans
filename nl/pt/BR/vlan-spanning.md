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


# VLAN Spanning
{: #vlan-spanning}

A ampliação de VLAN permite que todos os dispositivos em uma conta se comuniquem uns com os outros por meio da rede privada, independentemente dos dispositivos designados à VLAN.
{: #shortdesc}

## Entendendo a ampliação de VLAN
{: #understanding-vlan-spanning}


No {{site.data.keyword.Bluemix}}, a ampliação de VLAN pode ser usada para diversos propósitos diferentes e tem impacto na comunicação do dispositivo. Para saber mais sobre os conceitos básicos da ampliação de VLAN antes de começar, revise as informações a seguir.
{: shortdesc}

### Como a ampliação de VLAN funciona
{: #how-vlan-spanning-works}

Ao ativar a ampliação de VLAN, todo o seu tráfego encaminhado pode viajar entre todas as sub-redes privadas por todas as VLANs privadas de sua conta. Isso atende às necessidades de negócios que exigem a comunicação global de seu tráfego encaminhado. Por exemplo: ative a ampliação de VLAN se os dispositivos que residem em mais de uma sub-rede privada precisarem se comunicar, seja na mesma VLAN ou em VLANs diferentes.

Quando a ampliação está ativada, ela afeta toda a conta. Não é possível isentar nenhuma sub-rede, VLAN ou dispositivo de VLAN Spanning. Se você atualmente depende exclusivamente de sub-redes privadas para segregar servidores em funções ou camadas, a ativação da ampliação de VLAN removerá essa segregação.
{:note}

### Valores padrão
{: #vlan-spanning-default-values}

Por padrão, a ampliação de VLAN está desativada. Os dispositivos localizados em duas sub-redes privadas diferentes, na mesma VLAN ou em VLANs diferentes, não poderão enviar tráfego IP um para o outro.

### Serviços que normalmente requerem a ampliação de VLAN
{: #vlan-spanning-services}

Tutoriais específicos estão disponíveis para ajudá-lo a configurar a ampliação de VLAN para a sua situação. Consulte nossos links para [Outros recursos](/docs/infrastructure/vlans?topic=vlans-other-resources-vlan-spanning).


## Gerenciamento a ampliação de VLAN
{: #manage-vlan-spanning}

É possível ativar ou desativar a ampliação de VLAN para sua conta.
{: shortdesc}

Para atualizar a configuração de sua conta, siga essas etapas:

  1. Em seu navegador, abra o console do [{{site.data.keyword.Bluemix_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://{DomainName}/){: new_window} e efetue login em sua conta.
  2. No menu, selecione **Infraestrutura**. O Portal do Cliente é aberto.
  3. Na navegação do Portal do cliente, selecione **Rede > Gerenciamento de IP > VLANs**.
  4. Selecione a guia **Ampliação** para acessar a seção VLAN Spanning.
  5. Selecione o botão de opções **Ligar** ou **Desligar** conforme desejado para ativar ou desativar a ampliação de VLAN, respectivamente.

Alternar VLAN Spanning dentro de um curto período de tempo pode causar atrasos no aplicativo.
{:note}

A solicitação de atualização pode levar até 15 minutos para ser processada. Uma confirmação da mudança é exibida na tela. É possível atualizar suas configurações de ampliação de VLAN a qualquer momento, repetindo as etapas anteriores.
