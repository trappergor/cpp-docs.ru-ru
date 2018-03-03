---
title: "Константы кучи | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _HEAPBADPTR
- _HEAPEMPTY
- _HEAPBADBEGIN
- _HEAPOK
- _HEAPBADNODE
- _HEAPEND
dev_langs:
- C++
helpviewer_keywords:
- _HEAPOK constants
- _HEAPEND constants
- HEAPBADBEGIN constants
- _HEAPBADNODE constants
- HEAPBADNODE constants
- HEAPBADPTR constants
- _HEAPEMPTY constants
- HEAPEND constants
- HEAPOK constants
- HEAPEMPTY constants
- _HEAPBADBEGIN constants
- _HEAPBADPTR constants
- heap constants
ms.assetid: 3f751bb9-2dc4-486f-b5f5-9061c96d3754
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e2e1a15b371aa4f2997d453e2543123b279ac0df
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="heap-constants"></a>Константы кучи
## <a name="syntax"></a>Синтаксис  
  
```  
  
#include <malloc.h>  
  
```  
  
## <a name="remarks"></a>Примечания  
 Эти константы предоставляют возвращаемое значение, отображающее состояние кучи.  
  
|Константа|Значение|  
|--------------|-------------|  
|`_HEAPBADBEGIN`|Начальные сведения о заголовке не найдены или недопустимы.|  
|`_HEAPBADNODE`|Обнаружен недопустимый узел или куча повреждена.|  
|`_HEAPBADPTR`|Поле **_pentry** структуры **_HEAPINFO** не содержит допустимого указателя на кучу (только для подпрограммы `_heapwalk`).|  
|`_HEAPEMPTY`|Куча не инициализирована.|  
|`_HEAPEND`|Конец кучи успешно достигнут (только для подпрограммы `_heapwalk`).|  
|`_HEAPOK`|Куча согласована (только для подпрограмм `_heapset` и `_heapchk`). Пока без ошибок: структура **_HEAPINFO** содержит сведения о следующей записи (только для подпрограммы `_heapwalk`).|  
  
## <a name="see-also"></a>См. также  
 [_heapchk](../c-runtime-library/reference/heapchk.md)   
 [_heapset](../c-runtime-library/heapset.md)   
 [_heapwalk](../c-runtime-library/reference/heapwalk.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)