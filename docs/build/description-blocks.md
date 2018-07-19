---
title: Блоки описания | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- description blocks
- NMAKE program, description blocks
- blocks, description
ms.assetid: 1321f228-d389-40ac-b0cd-4f6e9293602b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0784f08c479a8c8f3968ef61a01431cd9e0ca71e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367112"
---
# <a name="description-blocks"></a>Блоки описания
Блок описания — строка зависимости следовать блок команд:  
  
```  
targets... : dependents...  
    commands...  
```  
  
 Строка зависимости определяет одну или несколько целей и ноль или более зависимых элементов. Целевой объект должен быть в начале строки. Допускаются отдельных целевых объектов из зависимых компонентов с помощью символа двоеточия (:), пробелы или знаки табуляции. Чтобы разделить строку, используйте обратную косую черту (\) после цели или зависимых. Если целевой объект не существует, имеет более раннюю временную метку, чем зависимый или является [псевдоцелью](../build/pseudotargets.md), NMAKE выполняет команды. Если зависимый является целевым объектом в другом месте и не существует или является устаревшей по отношению к собственным зависимостям, NMAKE обновляет зависимого перед обновлением текущей зависимости.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
 [Целевые объекты](../build/targets.md)  
  
 [Зависимые элементы](../build/dependents.md)  
  
## <a name="see-also"></a>См. также  
 [Справочник по программе NMAKE](../build/nmake-reference.md)