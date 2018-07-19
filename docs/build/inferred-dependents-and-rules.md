---
title: Вывести зависимости и правила | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rules, inferred
- inferred dependents in NMAKE
- inferred rules in NMAKE
- dependents, inferred
ms.assetid: 9381e74a-53d9-445c-836d-0ff7ef6112d9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aae09fd756e0eb4eab3031beb5b4cba8c4d35a40
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368048"
---
# <a name="inferred-dependents-and-rules"></a>Выводимые зависимости и правила
Если существует применимое правило вывода NMAKE предполагает выводимую зависимость для целевого объекта. Правило применяется, если:  
  
-   *toext* соответствует расширению целевого объекта.  
  
-   *fromext* совпадений, расширение файла, которые используют базовое имя целевого объекта и существует в текущем или указанном каталоге.  
  
-   *fromext* в [. СУФФИКСЫ](../build/dot-directives.md); никакие другие *fromext* в правило сопоставления имеет более высокий **. СУФФИКСЫ** приоритет.  
  
-   Отсутствует явная зависимость с более высокий **. СУФФИКСЫ** приоритет.  
  
 Выводимые зависимости может вызвать непредвиденные побочные эффекты. Если блок описания целевого объекта содержит команды, NMAKE выполняет эти команды вместо команды в правиле.  
  
## <a name="see-also"></a>См. также  
 [Правила вывода](../build/inference-rules.md)