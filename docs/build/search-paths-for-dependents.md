---
title: "Пути поиска для зависимых элементов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, dependents
- dependents, NMAKE
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cf777c89c78ab844b61138c30a5a9a25ca6b91d6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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