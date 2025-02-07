---
title: Git でのユーザ名を設定する
intro: 'Git は、アイデンティティによってコミットを関連付けるためにユーザ名を使います。 Git ユーザ名は、{% data variables.product.product_name %} ユーザ名と同じではありません。'
redirect_from:
  - /articles/setting-your-username-in-git
  - /github/using-git/setting-your-username-in-git
  - /github/getting-started-with-github/setting-your-username-in-git
  - /github/getting-started-with-github/getting-started-with-git/setting-your-username-in-git
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
shortTitle: Set your username
ms.openlocfilehash: c713f21fdf91269764dd97f15770e7996bf9f4f0
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2022
ms.locfileid: '145131272'
---
## Git ユーザー名について
`git config` コマンドを使って、Git コミットと関連付けられている名前を変更できます。 設定した新しい名前は、コマンドラインから {% data variables.product.product_name %} にプッシュするこれからのコミットに表示されます。 本名を非公開にしておきたい場合、Git ユーザ名としてどのテキストでも使うことができます。

`git config` を使った、Git コミットに関連付けられる名前の変更は、以降のコミットにだけ影響します。これまでのコミットに使った名前は変更されません。

## コンピューターにある *すべての* リポジトリ用に Git ユーザー名を設定する

{% data reusables.command_line.open_the_multi_os_terminal %}

2. {% data reusables.user-settings.set_your_git_username %}
   ```shell
   $ git config --global user.name "<em>Mona Lisa</em>"
   ```

3. {% data reusables.user-settings.confirm_git_username_correct %}
   ```shell
   $ git config --global user.name
   > Mona Lisa
   ```

## 単一のリポジトリ用に Git ユーザ名を設定する

{% data reusables.command_line.open_the_multi_os_terminal %}

2. 現在のワーキングディレクトリをGitコミットと関連付けた名前を設定したいローカルリポジトリに変更します。

3. {% data reusables.user-settings.set_your_git_username %}
   ```shell
   $ git config user.name "<em>Mona Lisa</em>"
   ```

3. {% data reusables.user-settings.confirm_git_username_correct %}
   ```shell
   $ git config user.name
   > Mona Lisa
   ```

## 参考資料

- 「[コミット メール アドレスを設定する](/articles/setting-your-commit-email-address)」
- [_Pro Git_ ブックの「Git の構成」](https://git-scm.com/book/en/Customizing-Git-Git-Configuration)
