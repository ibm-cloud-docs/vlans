---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-27"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Ativar ou desativar a ampliação de VLAN

Às vezes, múltiplas VLANs de rede privada podem existir em uma única conta do cliente. No entanto, dispositivos de rede não conseguem se comunicar uns com os outros na rede privada se eles não existirem na mesma VLAN. A ampliação de VLAN permite que todos os dispositivos em uma conta se comuniquem entre si por meio da rede privada, independentemente de sua VLAN designada. 

O serviço de ampliação de VLAN se aplica a todos os dispositivos na conta; a ampliação não pode ser aplicada a VLANs específicas ou a dispositivos específicos. A ampliação da VLAN pode ser ativada ou desativada conforme necessário e leva aproximadamente 15 minutos para processar assim que uma mudança na configuração é feita. Siga as etapas fornecidas neste artigo para ativar ou desativar a ampliação de VLAN em uma conta.


1. Em seu navegador, abra o [Portal do cliente ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://control.softlayer.com/){: new_window} e efetue login em sua conta.
2. Na navegação do Portal do cliente, selecione **Rede > Gerenciamento de IP > VLANs**.
3. Selecione a guia **Ampliação** para acessar a seção Ampliação de VLAN.
4. Selecione o botão de opções **Ativado** para permitir a ampliação de VLAN. Escolha o botão de opções **Desativado** para desativar a ampliação de VLAN.

## O que acontece em seguida

Após atualizar as seleções de ampliação da VLAN, a solicitação poderá levar até 15 minutos para processar. A confirmação da mudança aparecerá abaixo da guia Ampliação. Se você ativar a ampliação de VLAN, os dispositivos poderão se comunicar entre si por meio das VLANs usando a rede privada. Se você desativar a ampliação, os dispositivos poderão se conectar entre si apenas se residirem na mesma VLAN; a comunicação entre VLANs não estará mais ativada. As configurações de ampliação de VLAN podem ser atualizadas a qualquer momento repetindo as etapas fornecidas nesse artigo. **Nota:** alternar entre as configurações de ampliação de VLAN em um curto período de tempo pode resultar em um atraso na aplicação das configurações.
