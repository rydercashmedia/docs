---
ms.openlocfilehash: 9b9749a9b1d8405deadafdb29203b9537900813e
ms.sourcegitcommit: fcf3546b7cc208155fb8acdf68b81be28afc3d2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2022
ms.locfileid: "145121546"
---
Para resolver problemas, primero decide si quieres utilizar un submódulo, lo cual es un proyecto de Git dentro de otro proyecto de Git; ya que estos a veces se crean por accidente.

Si no quiere usar un submódulo, elimínelo y reemplace <em>RUTA-DEL-SUBMÓDULO</em> con la ruta del submódulo:
```shell
$ git submodule deinit <em>PATH-TO-SUBMODULE</em>
$ git rm <em>PATH-TO-SUBMODULE</em>
$ git commit -m "Remove submodule"
$ rm -rf .git/modules/<em>PATH-TO-SUBMODULE</em>
```
