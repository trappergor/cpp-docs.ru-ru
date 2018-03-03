---
title: "Вывести зависимости и правила | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- rules, inferred
- inferred dependents in NMAKE
- inferred rules in NMAKE
- dependents, inferred
ms.assetid: 9381e74a-53d9-445c-836d-0ff7ef6112d9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fe7c49607f466d8fd1d333883414b24d7837432b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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