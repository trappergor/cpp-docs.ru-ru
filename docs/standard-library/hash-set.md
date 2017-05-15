---
title: "&lt;hash_set&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <hash_set>
- std.<hash_set>
- std::<hash_set>
dev_langs:
- C++
helpviewer_keywords:
- hash_set header
ms.assetid: 6b556967-c808-4869-9b4d-f9e030864435
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 3941ccdd426e88e93591e3e759fcf9219f79d8ab
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="lthashsetgt"></a>&lt;hash_set&gt;
> [!NOTE]
>  Этот заголовок устарел. Вместо него следует использовать [<unordered_set>](../standard-library/unordered-set.md).  
  
 Определяет контейнер шаблонных классов hash_set и hash_multiset и их поддерживаемые шаблоны.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#include <hash_set>  
  
```  
  
## <a name="remarks"></a>Примечания  
  
### <a name="operators"></a>Операторы  
  
|Версия hash_set|Версия hash_multiset|Описание|  
|-----------------------|----------------------------|-----------------|  
|[operator!= (hash_set)](../standard-library/hash-set-operators.md#op_neq)|[operator!= (hash_multiset)](../standard-library/hash-set-operators.md#op_neq)|Проверяет неравенство объекта hash_set или hash_multiset слева от оператора объекту hash_set или hash_multiset справа от оператора.|  
|[operator== (hash_set)](../standard-library/hash-set-operators.md#op_eq_eq)|[operator== (hash_multiset)](../standard-library/hash-set-operators.md#op_eq_eq)|Проверяет равенство объекта hash_set или hash_multiset слева от оператора объекту hash_set или hash_multiset справа от оператора.|  
  
### <a name="specialized-template-functions"></a>Специализированные функции шаблонов  
  
|Версия hash_set|Версия hash_multiset|Описание|  
|-----------------------|----------------------------|-----------------|  
|[swap (hash_set)](../standard-library/hash-set-functions.md#swap)|[swap (hash_multiset)](../standard-library/hash-set-functions.md#swap_hash_multiset)|Меняет местами элементы двух объектов hash_set или hash_multiset.|  
  
### <a name="classes"></a>Классы  
  
|||  
|-|-|  
|[Класс hash_compare](../standard-library/hash-compare-class.md)|Описывает объект, который может использоваться любыми hash-ассоциативными контейнерами (hash_map, hash_multimap, hash_set или hash_multiset) как объект параметра **Traits** по умолчанию для сортировки и хэширования элементов в них.|  
|[Класс hash_set](../standard-library/hash-set-class.md)|Используется для хранения и быстрого извлечения данных из коллекции, в которой значения элементов должны быть уникальными и в которой они служат в качестве значений ключей.|  
|[Класс hash_multiset](../standard-library/hash-multiset-class.md)|Используется для хранения и быстрого извлечения данных из коллекции, в которой значения элементов должны быть уникальными и в которой они служат в качестве значений ключей.|  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)




