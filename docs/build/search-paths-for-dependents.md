---
title: Пути поиска для зависимых элементов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, dependents
- dependents, NMAKE
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 577fc7e44bfff35cf7efdcff20dc4cdca1c7001e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="search-paths-for-dependents"></a>Пути поиска для зависимых элементов
Каждый зависимый элемент имеет дополнительный путь поиска, указанный следующим образом:  
  
## <a name="syntax"></a>Синтаксис  
  
```  
{directory[;directory...]}dependent  
```  
  
## <a name="remarks"></a>Примечания  
 NMAKE ищет зависимые элементы сначала в текущем каталоге, а затем в папках, в указанном порядке. Макрос можно указать всех или части пути поиска. Заключите имя каталога в фигурные скобки ({}); несколько каталогов разделяются точкой с запятой (;). Допускаются пробелы или табуляцию.  
  
## <a name="see-also"></a>См. также  
 [Зависимые элементы](../build/dependents.md)