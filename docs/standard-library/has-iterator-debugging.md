---
title: "_HAS_ITERATOR_DEBUGGING | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _HAS_ITERATOR_DEBUGGING
dev_langs: C++
helpviewer_keywords: _HAS_ITERATOR_DEBUGGING
ms.assetid: 90077dbb-8a76-4963-83a6-29f4854007a8
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7c680338fa84fa0f00e01ea4612d07c851570a36
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="hasiteratordebugging"></a>_HAS_ITERATOR_DEBUGGING  
  
Этот макрос, который был заменен макросом [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), определяет, включена ли функция отладки итераторов в отладочной сборке. По умолчанию отладка итераторов включена в отладочных сборках и отключена в окончательных сборках. Дополнительные сведения см. в статье [Debug Iterator Support](../standard-library/debug-iterator-support.md) (Поддержка итераторов при отладке).  
  
> [!IMPORTANT]
> Непосредственное использование макроса `_HAS_ITERATOR_DEBUGGING` не рекомендуется. Вместо этого, для управления параметрами отладки итераторов используйте `_ITERATOR_DEBUG_LEVEL`. Дополнительные сведения см. в разделе [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).  
  
## <a name="remarks"></a>Примечания  
Чтобы включить отладку итераторов в отладочных сборках, установите для макроса `_ITERATOR_DEBUG_LEVEL` значение 2. Это эквивалентно ситуации, когда для `_HAS_ITERATOR_DEBUGGING` установлено значение 1, или макрос включен:  
  
```  
#define _ITERATOR_DEBUG_LEVEL 2  
```  
  
для `_ITERATOR_DEBUG_LEVEL` нельзя установить значение 2 (и для `_HAS_ITERATOR_DEBUGGING` нельзя установить значение 1) в коммерческих сборках.  
  
Чтобы отключить итераторы при отладке в отладочных сборках, установите для `_ITERATOR_DEBUG_LEVEL` значение 0 или 1. Это эквивалентно ситуации, когда для `_HAS_ITERATOR_DEBUGGING` установлено значение 0, или макрос выключен:  
  
```  
#define _ITERATOR_DEBUG_LEVEL 0  
```  
  
## <a name="see-also"></a>См. также  
 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)   
 [Поддержка итераторов отладки](../standard-library/debug-iterator-support.md)   
 [Проверяемые итераторы](../standard-library/checked-iterators.md)   
 [Безопасные библиотеки: стандартная библиотека C++](../standard-library/safe-libraries-cpp-standard-library.md)

