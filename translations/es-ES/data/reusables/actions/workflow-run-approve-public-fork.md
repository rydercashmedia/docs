---
ms.openlocfilehash: 59e70683dad451b603d2d34286976bfaa8d1d9c8
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2022
ms.locfileid: "145069400"
---
Cualquiera puede bifurcar un repositorio público y luego emitir una solicitud de cambios que proponga cambios en los flujos de trabajo de {% data variables.product.prodname_actions %} del mismo. Aunque los flujos de trabajo de las bifurcaciones no tienen acceso a datos sensibles tales como los secretos, pueden ser molestos para los mantenedores si se modifican para fines de abuso.

Para ayudar a prevenir esto, los flujos de trabajo sobre las solicitudes de cambio en los repositorios públicos de algunos contribuyentes no se ejecutarán automáticamente y podrían necesitar aprobarse primero. Predeterminadamente, todos los contribuyentes de primera vez necesitan aprobación para ejecutar flujos de trabajo.

{% note %}

**Nota:** Los flujos de trabajo desencadenados por eventos `pull_request_target` se ejecutan en el contexto de la rama base. Ya que la rama base se considera como confiable, los flujos de trabajo que activen estos eventos siempre se ejecutarán, sin importar los ajustes de aprobaciones.

{% endnote %}
