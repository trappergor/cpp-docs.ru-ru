---
title: "_SECURE_SCL | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _SECURE_SCL
dev_langs:
- C++
helpviewer_keywords:
- _SECURE_SCL
ms.assetid: 4ffbc788-cc12-4c6a-8cd7-490081675086
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 9e2bfb1095c28ea3592c5af2b89cb2fbeddcb60c
ms.openlocfilehash: f3712b4417c0fed972d9a20b6d82479561cce4b0
ms.lasthandoff: 02/24/2017

---
# <a name="securescl"></a>_SECURE_SCL
  
Этот макрос, заменяемый [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), определяет, включены ли [Проверяемые итераторы](../standard-library/checked-iterators.md). По умолчанию проверяемые итераторы включены в отладочных сборках и отключены в окончательных сборках.  
  
> [!IMPORTANT]
> Непосредственное использование макроса `_SECURE_SCL` не рекомендуется. Вместо этого для контроля параметров проверяемых итераторов следует использовать `_ITERATOR_DEBUG_LEVEL`. Дополнительные сведения см. в разделе [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).  
  
## <a name="remarks"></a>Примечания  
  
Если проверяемые итераторы включены, небезопасный итератор может вызвать ошибку во время выполнения и программа будет завершена. Чтобы включить проверяемые итераторы, задайте `_ITERATOR_DEBUG_LEVEL` равным 1 или 2. Это эквивалентно ситуации, когда для `_SECURE_SCL` установлено значение 1, или макрос включен:  
  
```  
#define _ITERATOR_DEBUG_LEVEL 1  
```  
  
Чтобы выключить проверяемые итераторы, задайте `_ITERATOR_DEBUG_LEVEL` равным 0. Это эквивалентно ситуации, когда для `_SECURE_SCL` установлено значение 0, или макрос выключен:  
  
```  
#define _ITERATOR_DEBUG_LEVEL 0  
```  
  
Сведения о том, как отключить предупреждения о проверяемых итераторах, см. в разделе [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).  
  
## <a name="see-also"></a>См. также  
[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)   
[Проверяемые итераторы](../standard-library/checked-iterators.md)   
[Поддержка итераторов отладки](../standard-library/debug-iterator-support.md)   
[Безопасные библиотеки: стандартная библиотека C++](../standard-library/safe-libraries-cpp-standard-library.md)


