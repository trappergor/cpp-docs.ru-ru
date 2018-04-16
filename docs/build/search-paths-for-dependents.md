---
title: Пути поиска для зависимых элементов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, dependents
- dependents, NMAKE
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f6093db4ac8e0c88dfe6e4b5a5463e5ee8d24349
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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