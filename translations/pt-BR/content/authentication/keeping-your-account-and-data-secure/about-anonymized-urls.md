---
title: Sobre URLs anônimas
intro: 'Se você fizer o upload de uma imagem ou vídeo para {% data variables.product.product_name %}, a URL da imagem ou vídeo será modificada para que suas informações não sejam rastreáveis.'
redirect_from:
  - /articles/why-do-my-images-have-strange-urls
  - /articles/about-anonymized-image-urls
  - /authenticating-to-github/about-anonymized-image-urls
  - /github/authenticating-to-github/about-anonymized-urls
  - /github/authenticating-to-github/keeping-your-account-and-data-secure/about-anonymized-urls
versions:
  fpt: '*'
  ghec: '*'
topics:
  - Identity
  - Access management
ms.openlocfilehash: b96c01144d28d668d33e96e4067801395aaa8275
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/05/2022
ms.locfileid: '145095800'
---
Para hospedar suas imagens, o {% data variables.product.product_name %} usa o [projeto de código aberto Camo](https://github.com/atmos/camo). A Camo gera um proxy de URL anônimo para cada arquivo que oculta os detalhes do seu navegador e informações relacionadas de outros usuários. A URL começa com `https://<subdomain>.githubusercontent.com/`, com subdomínios diferentes, dependendo de como você carregou a imagem. 

Os vídeos também recebem URLs anônimas com o mesmo formato que as URLs da imagem, mas não são processados através da Camo. Isto ocorre porque {% data variables.product.prodname_dotcom %} não é compatível vídeos hospedados externamente. Portanto, a URL anônima é um link para o vídeo enviado hospedado por {% data variables.product.prodname_dotcom %}.

Qualquer pessoa que receber a sua URL anônima, direta ou indiretamente, poderá visualizar a sua imagem ou vídeo. Para manter arquivos de mídia sensíveis privados, restrinja-os a uma rede privada ou a um servidor que exige autenticação em vez de usar a Camo.

## Solucionar problemas com o Camo

As imagens que são processadas por meio do Camo raramente não aparecem no {% data variables.product.prodname_dotcom %}. Veja a seguir algumas etapas que podem ser seguidas para determinar onde está o problema.

{% windows %}

{% tip %}

Os usuários do Windows precisarão usar o Git PowerShell (que é instalado com o [{% data variables.product.prodname_desktop %}](https://desktop.github.com/)) ou baixar o [cURL para Windows](http://curl.haxx.se/download.html).

{% endtip %}

{% endwindows %}

### Uma imagem não está sendo exibida

Se uma imagem estiver sendo exibida no seu navegador mas não em {% data variables.product.prodname_dotcom %}, você poderá tentar solicitá-la localmente.

{% data reusables.command_line.open_the_multi_os_terminal %}
1. Solicite os cabeçalhos de imagem usando `curl`.
  ```shell
  $ curl -I https://www.my-server.com/images/some-image.png
  > HTTP/2 200
  > Date: Fri, 06 Jun 2014 07:27:43 GMT
  > Expires: Sun, 06 Jul 2014 07:27:43 GMT
  > Content-Type: image/x-png
  > Server: Google Frontend
  > Content-Length: 6507
  ```
3. Verifique o valor de `Content-Type`. Nesse caso, use `image/x-png`.
4. Verifique esse tipo de conteúdo em relação [à lista de tipos com suporte do Camo](https://github.com/atmos/camo/blob/master/mime-types.json).

Se o tipo de conteúdo não for compatível com o Camo, você poderá tentar várias ações:
  * Se tiver posse do servidor que está hospedando a imagem, modifique-o para que ele retorne um tipo de conteúdo correto para imagens.
  * Se estiver usando um serviço externo para hospedar imagens, entre em contato com o suporte do serviço em questão.
  * Faça uma pull request ao Camo a fim de adicionar seu tipo de conteúdo à lista.

### Uma imagem que foi alterada recentemente não está atualizando

Se você alterou uma imagem recentemente e ela está sendo exibida no navegador, mas não no {% data variables.product.prodname_dotcom %}, tente redefinir o cache da imagem.

{% data reusables.command_line.open_the_multi_os_terminal %}
1. Solicite os cabeçalhos de imagem usando `curl`.
  ```shell
  $ curl -I https://www.my-server.com/images/some-image.png
  > HTTP/2 200
  > Expires: Fri, 01 Jan 1984 00:00:00 GMT
  > Content-Type: image/png
  > Content-Length: 2339
  > Server: Jetty(8.y.z-SNAPSHOT)
  ```

Verifique o valor de `Cache-Control`. Neste exemplo, não há nenhum `Cache-Control`. Nesse caso:
  * Se você é o proprietário do servidor que está hospedando a imagem, modifique-a para que ela retorne um `Cache-Control` igual a `no-cache` para as imagens.
  * Se estiver usando um serviço externo para hospedar imagens, entre em contato com o suporte do serviço em questão.

 Se `Cache-Control` *estiver* definido como `no-cache`, entre em contato com o {% data variables.contact.contact_support %} ou pesquise o {% data variables.contact.community_support_forum %}.

### Remover uma imagem do cache do Camo

A limpeza do cache força os usuários do {% data variables.product.prodname_dotcom %} a solicitar novamente a imagem. Portanto, você deve usá-la bem moderadamente e somente no caso em que as etapas acima não funcionarem.

{% data reusables.command_line.open_the_multi_os_terminal %}
1. Limpe a imagem usando `curl -X PURGE` na URL do Camo.
  ```shell
  $ curl -X PURGE https://camo.githubusercontent.com/4d04abe0044d94fefcf9af2133223....
  > {"status": "ok", "id": "216-8675309-1008701"}
  ```

### Exibir imagens em redes privadas

Se uma imagem estiver sendo fornecida por uma rede privada ou um servidor que exige autenticação, ela não poderá ser exibida pelo {% data variables.product.prodname_dotcom %}. Na verdade, a imagem não pode ser exibida pelos usuários sem que eles façam login no servidor.

Para corrigir isso, mova a imagem para um serviço que esteja disponível publicamente.

## Leitura adicional

- "[Como criar um proxy para imagens do usuário](https://github.com/blog/1766-proxying-user-images)" no {% data variables.product.prodname_blog %}
