---
title: "&lt;hash_map&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.<hash_map>
- <hash_map>
- std::<hash_map>
dev_langs:
- C++
helpviewer_keywords:
- hash_map header
ms.assetid: 0765708a-a668-42a2-9800-654c857bdcc2
caps.latest.revision: 27
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
translationtype: Machine Translation
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: 3f9a4705d946831ddee15116676fde9e433288f7
ms.lasthandoff: 02/24/2017

---
# <a name="lthashmapgt"></a>&lt;hash_map&gt;
> [!NOTE]
>  Этот заголовок устарел. Вместо него следует использовать [<unordered_map>](../standard-library/unordered-map.md).  
  
 Определяет контейнер шаблонных классов hash_map и hash_multimap и их поддерживаемые шаблоны.  
  
 В Visual C++ .NET 2003 члены файлов заголовков <hash_map> и <hash_set> больше не находятся в пространстве имен std. Они перемещены в пространство имен stdext. Дополнительные сведения см. в разделе [Пространство имен stdext](../standard-library/stdext-namespace.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#include <hash_map>  
  
```  
  
### <a name="operators"></a>Операторы  
  
|Версия hash_map|Версия hash_multimap|Описание|  
|-----------------------|----------------------------|-----------------|  
|[operator!= (hash_map)](../standard-library/hash-map-operators.md#operator_neq__hash_map_)|[ operator!= (hash_multimap)](../standard-library/hash-map-operators.md#operator_neq)|Проверяет неравенство объекта hash_map или hash_multimap слева от оператора объекту hash_map или hash_multimap справа от оператора.|  
|[ operator== (hash_map)](http://msdn.microsoft.com/en-us/f933cb1c-934d-43f5-aa9e-0b325eb95b85)|[ operator== (hash_multimap)](http://msdn.microsoft.com/en-us/3fa378b1-0250-4e3f-a130-dc14103fc5e9)|Проверяет равенство объекта hash_map или hash_multimap слева от оператора объекту hash_map или hash_multimap справа от оператора.|  
  
### <a name="specialized-template-functions"></a>Специализированные функции шаблонов  
  
|Версия hash_map|Версия hash_multimap|Описание|  
|-----------------------|----------------------------|-----------------|  
|[swap (hash_map)](../standard-library/hash-map-class.md#hash_map__swap)|[swap (hash_multimap)](../standard-library/hash-multimap-class.md#hash_multimap__swap)|Меняет местами элементы двух объектов hash_map или hash_multimap.|  
  
### <a name="classes"></a>Классы  
  
|||  
|-|-|  
|[Класс hash_compare](../standard-library/hash-compare-class.md)|Описывает объект, который может использоваться любыми hash-ассоциативными контейнерами (hash_map, hash_multimap, hash_set или hash_multiset) как объект параметра **Traits** по умолчанию для сортировки и хэширования элементов в них.|  
|[Класс value_compare](../standard-library/value-compare-class.md)|Предоставляет объект функции, который может сравнивать элементы hash_map путем сравнения значения ключей для определения относительного порядка в hash_map.|  
|[Класс hash_map](../standard-library/hash-map-class.md)|Используется для хранения и быстрого считывания данных из коллекции, в которой каждый элемент — это пара, которая имеет отсортированный уникальный ключ и связанное с ним значение.|  
|[Класс hash_multimap](../standard-library/hash-multimap-class.md)|Используется для хранения и быстрого считывания данных из коллекции, в которой каждый элемент — это пара, которая имеет ключ, значение которого не должно быть уникальным, и связанное с ним значение.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<hash_map>  
  
 **Пространство имен:** stdext  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)




