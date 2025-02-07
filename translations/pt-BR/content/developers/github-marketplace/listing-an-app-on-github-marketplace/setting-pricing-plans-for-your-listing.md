---
title: Definir planos de cobrança para sua listagem
intro: 'Quando você listar seu aplicativo em {% data variables.product.prodname_marketplace %}, você poderá escolher fornecer seu aplicativo como um serviço grátis ou vender seu aplicativo. Se você pretende vender seu aplicativo, você pode criar planos de preços diferentes para diferentes níveis de recursos.'
redirect_from:
  - /apps/adding-integrations/managing-pricing-and-payments-for-a-github-marketplace-listing/setting-a-github-marketplace-listing-s-pricing-plan
  - /apps/marketplace/managing-pricing-and-payments-for-a-github-marketplace-listing/setting-a-github-marketplace-listing-s-pricing-plan
  - /apps/marketplace/pricing-payments-and-free-trials/setting-a-github-marketplace-listing-s-pricing-plan
  - /apps/adding-integrations/managing-pricing-and-payments-for-a-github-marketplace-listing/about-github-marketplace-pricing-plans
  - /apps/marketplace/managing-pricing-and-payments-for-a-github-marketplace-listing/about-github-marketplace-pricing-plans
  - /apps/marketplace/pricing-payments-and-free-trials/about-github-marketplace-pricing-plans
  - /apps/adding-integrations/managing-pricing-and-payments-for-a-github-marketplace-listing/changing-a-github-marketplace-listing-s-pricing-plan
  - /apps/marketplace/managing-pricing-and-payments-for-a-github-marketplace-listing/changing-a-github-marketplace-listing-s-pricing-plan
  - /apps/marketplace/managing-github-marketplace-listings/changing-a-github-marketplace-listing-s-pricing-plan
  - /apps/marketplace/listing-on-github-marketplace/setting-a-github-marketplace-listing-s-pricing-plan
  - /marketplace/listing-on-github-marketplace/setting-a-github-marketplace-listing-s-pricing-plan
  - /developers/github-marketplace/setting-pricing-plans-for-your-listing
versions:
  fpt: '*'
  ghec: '*'
topics:
  - Marketplace
shortTitle: Set listing pricing plans
ms.openlocfilehash: bc8d84a55c9597da051ab11752dd7e412761d5d7
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/05/2022
ms.locfileid: '145083941'
---
## Sobre a configuração dos planos de preços

{% data variables.product.prodname_marketplace %} oferece vários tipos diferentes de planos de preços. Para obter informações detalhadas, confira "[Planos de preços do {% data variables.product.prodname_marketplace %}](/developers/github-marketplace/pricing-plans-for-github-marketplace-apps)".

Para oferecer um plano pago para seu aplicativo, este deve ser pertencente a uma organização que tenha concluído o processo de verificação de editor e atendido a certos critérios. Para obter mais informações, confira "[Como solicitar a verificação de editor para sua organização](/developers/github-marketplace/applying-for-publisher-verification-for-your-organization)" e "[Requisitos para listar um aplicativo no {% data variables.product.prodname_marketplace %}](/marketplace/getting-started/requirements-for-listing-an-app-on-github-marketplace/)".

Se seu aplicativo já foi publicado com um plano pago e você é um editor verificado, você poderá publicar um novo plano pago a partir da página "Editar um plano de preços" nas configurações da listagem do seu aplicativo do Marketplace. 

![Botão Publicar este plano](/assets/images/marketplace/publish-this-plan-button.png)

Se seu aplicativo já foi publicado com um plano pago, mas você não é um editor verificado, você não poderá publicar um novo plano pago até que um editor seja verificado. Para obter mais informações sobre como se tornar um fornecedor verificado, confira "[Como solicitar a verificação de fornecedor para sua organização](/developers/github-marketplace/applying-for-publisher-verification-for-your-organization)".

## Sobre como salvar planos de preços

Você pode salvar planos de preços com status de rascunho ou publicado. Se você não enviou seu anúncio de {% data variables.product.prodname_marketplace %} para aprovação, um plano publicado funcionará da mesma forma que um plano provisório até que o seu anúncio seja aprovado e exibido em {% data variables.product.prodname_marketplace %}. Os planos de rascunho permitem criar e salvar novos planos de preços sem torná-los disponíveis na sua página de anúncio de {% data variables.product.prodname_marketplace %}. Depois de publicar um plano de preços em um anúncio publicado, os clientes poderão comprar imediatamente. Você pode publicar até 10 planos de preços.

Para obter diretrizes sobre a cobrança de clientes, confira "[Cobrança de clientes](/developers/github-marketplace/billing-customers)".

## Criar planos de preços

Para criar um plano de preços para sua listagem do {% data variables.product.prodname_marketplace %}, clique em **Planos e preços** na barra lateral esquerda da [página de listagem do {% data variables.product.prodname_marketplace %}](https://github.com/marketplace/manage). Para obter mais informações, confira "[Como criar uma listagem de rascunho do {% data variables.product.prodname_marketplace %}](/marketplace/listing-on-github-marketplace/creating-a-draft-github-marketplace-listing/)".

Ao clicar em **Novo plano de rascunho**, você verá um formulário que permite personalizar seu plano de preços. Você precisará configurar os seguintes campos para criar um plano de preços:

- **Nome do plano** – O nome do seu plano de preços será exibido na página de aterrissagem do seu aplicativo do {% data variables.product.prodname_marketplace %}. Você pode personalizar o nome do seu plano de preços para se alinhar com os recursos do plano, o tamanho da empresa que usará o plano ou qualquer coisa que desejar.

- **Modelos de preços** – Há três tipos de planos de preços: gratuito, de taxa fixa e por unidade. Todos os planos exigem que você processe novos eventos de compra e cancelamento da API do marketplace. Além disso, para os planos pagos:

  - Você deve definir um preço para as assinaturas mensais e anuais em dólar.
  - Seu aplicativo deve processar eventos de mudança de plano.
  - Você deve solicitar verificação para publicar um anúncio com um plano pago.
  - {% data reusables.marketplace.marketplace-pricing-free-trials %}

  Para obter informações detalhadas, confira "[Planos de preços para aplicativos do {% data variables.product.prodname_marketplace %}](/developers/github-marketplace/pricing-plans-for-github-marketplace-apps)" e "[Como usar a API do {% data variables.product.prodname_marketplace %} no seu aplicativo](/developers/github-marketplace/using-the-github-marketplace-api-in-your-app)".

- **Disponível para** – Os planos de preços do {% data variables.product.prodname_marketplace %} podem ser aplicados a **Contas pessoais e organizacionais**, **Somente contas pessoais** ou **Somente contas de organização**. Por exemplo, se o seu plano de preços for por unidade e fornecer várias estações, você selecionará a opção **Somente contas de organização**, porque não há nenhuma forma de atribuir estações a pessoas de uma organização em uma conta pessoal.

- **Descrição breve** – Escreva um breve resumo dos detalhes do plano de preços. A descrição pode incluir o tipo de cliente para o qual o plano se destina ou os recursos que o plano inclui.

- **Marcadores** – Você pode escrever até quatro marcadores que incluem mais detalhes sobre o seu plano de preços. Os marcadores podem incluir casos de uso do seu aplicativo ou listar informações mais detalhadas sobre as características ou os recursos incluídos no plano.

{% data reusables.marketplace.free-plan-note %}

## Alterar um plano de preços da listagem do {% data variables.product.prodname_marketplace %}

Se um plano de preços para o seu anúncio de {% data variables.product.prodname_marketplace %} não for mais necessário, ou se você precisar ajustar os detalhes de preços, você poderá removê-lo.

![Botão para remover o seu plano de preços](/assets/images/marketplace/marketplace_remove_this_plan.png)

Depois de publicar um plano de preços para um aplicativo que já está listado em {% data variables.product.prodname_marketplace %}, você não poderá fazer alterações no plano. Em vez disso, você precisará remover o plano de preços e criar um novo plano. Os clientes que já compraram o plano de preços removido continuarão a usá-lo até que optem por sair o plano e passar para um novo plano de preços. Para obter mais informações sobre os planos de preços, confira "[Planos de preços do {% data variables.product.prodname_marketplace %}](/marketplace/selling-your-app/github-marketplace-pricing-plans/)".

Depois de remover um plano de preços, os usuários não poderão comprar seu aplicativo que usa esse plano. Os usuários existentes no plano de preços removido continuarão no plano até que cancelem sua assinatura do plano.

{% note %}

**Observação:** o {% data variables.product.product_name %} não pode remover usuários de um plano de preços removido. Você pode realizar uma campanha para incentivar os usuários a atualizar ou fazer downgrade do plano de preços removido para um novo plano de preços.

{% endnote %}

Você pode desativar os testes grátis do GitHub Marketplace sem remover o plano de preços, mas isso impede que você inicie futuros testes grátis para esse plano. Se você optar por desativar os testes grátis para um plano de preços, os usuários já inscritos poderão concluir o seu teste gratuito.

Depois de remover um plano de preços, você poderá criar um novo plano com o mesmo nome do plano de preços removido. Por exemplo, se você tem um plano de preços "Pro", mas precisa alterar o preço fixo, você poderá remover o plano de preços "Pro" e criar um novo plano de preços "Pro" com um preço atualizado. Os usuários poderão comprar o novo plano de preços imediatamente.

Se você não for um editor verificado, você não poderá alterar um plano de preços para o seu aplicativo. Para obter mais informações sobre como se tornar um fornecedor verificado, confira "[Como solicitar a verificação de fornecedor para sua organização](/developers/github-marketplace/applying-for-publisher-verification-for-your-organization)".
