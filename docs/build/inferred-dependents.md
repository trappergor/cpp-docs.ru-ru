---
title: Выводимые зависимости | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inferred dependents in NMAKE
- dependents, inferred
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a86ed1a8fe6c97ae11af50f59cb639ef6fd7c1da
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367902"
---
# <a name="inferred-dependents"></a>Выводимые зависимости
Выводимая зависимость создается правило определения и оценивается перед явными зависимостями. Если выводимая зависимость устарела по отношению к цели, NMAKE вызывает для этой зависимости блок команд. Если выводимая зависимость не существует или является устаревшей по отношению к собственным зависимостям, программа NMAKE сначала обновляет эту зависимость. Дополнительные сведения о выводимых зависимостях см. в разделе [правила вывода](../build/inference-rules.md).  
  
## <a name="see-also"></a>См. также  
 [Зависимые элементы](../build/dependents.md)