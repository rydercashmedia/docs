---
title: 'Error: We''re doing an SSH key audit'
intro: このエラーは、Git 操作のために使用中の SSH キーが未検証であることを意味します。
redirect_from:
  - /articles/error-we-re-doing-an-ssh-key-audit
  - /articles/error-were-doing-an-ssh-key-audit
  - /github/authenticating-to-github/error-were-doing-an-ssh-key-audit
  - /github/authenticating-to-github/troubleshooting-ssh/error-were-doing-an-ssh-key-audit
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - SSH
shortTitle: SSH key audit
ms.openlocfilehash: 8683f5506fc2a026c11f22f2086de2308d096906
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2022
ms.locfileid: '145088169'
---
未検証のキーを使用して Git 操作を実行すると、SSH キーの監査を行うように求めるメッセージが表示されます。

```shell
ERROR: We're doing an SSH key audit.
Reason: unverified due to lack of use
Please visit https://github.com/settings/ssh
to approve this key so we know it's safe.
Fingerprint: ab:08:46:83:ff:f6:c4:f8:a9:4e:68:6b:94:17:f2:46
fatal: could not read from remote repository
```
## 問題の解決

これを修正するには、[SSH キーを確認](/articles/reviewing-your-ssh-keys)し、未検証のキーを拒否または承認する必要があります。 エラーメッセージ内の URL リンクをクリックすると、SSH の設定ページに移動し、未検証の SSH キーが SSH キーリスト内で強調表示されます。
