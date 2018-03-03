---
title: "Блоки описания | Документы Microsoft"
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
- description blocks
- NMAKE program, description blocks
- blocks, description
ms.assetid: 1321f228-d389-40ac-b0cd-4f6e9293602b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 37f095f5ae46e4b555f1d3f7996bd5f357e58ee2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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