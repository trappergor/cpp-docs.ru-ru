---
title: "&lt;map&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::<map>
- std.<map>
- <map>
dev_langs:
- C++
helpviewer_keywords:
- map header
ms.assetid: bbf76680-7362-456e-88fa-ecda93561b6a
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: fad398e9f18c2f45de7e071be464e3eff2e9243e
ms.lasthandoff: 02/24/2017

---
# <a name="ltmapgt"></a>&lt;map&gt;
Определяет классы шаблонов контейнеров map и multimap и их вспомогательные шаблоны.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#include <map>  
  
```  
  
## <a name="members"></a>Члены  
  
### <a name="operators"></a>Операторы  
  
|Версия Map|Версия Multimap|Описание|  
|-----------------|----------------------|-----------------|  
|[operator!= (map)](../standard-library/map-operators.md#operator_neq)|[operator!= (multimap)](../standard-library/map-operators.md#operator_neq)|Проверяет неравенство объекта map или multimap слева от оператора объекту map или multimap справа от оператора.|  
|[оператор< (map)](../standard-library/map-operators.md#operator_eq_eq)|[оператор< (multimap)](../standard-library/map-operators.md#operator_eq_eq)|Проверяет, меньше ли объект map или multimap слева от оператора объекта map или multimap справа от оператора.|  
|[оператор<= (map)](../standard-library/map-operators.md#operator_lt_)|[оператор\<= (multimap)](../standard-library/map-operators.md#operator_lt_)|Проверяет, меньше или равен объект map или multimap слева от оператора объекту map или multimap справа от оператора.|  
|[оператор== (map)](../standard-library/map-operators.md#operator_lt__eq)|[оператор== (multimap)](../standard-library/map-operators.md#operator_lt__eq)|Проверяет равенство объекта map или multimap слева от оператора объекту map или multimap справа от оператора.|  
|[оператор> (map)](../standard-library/map-operators.md#operator_gt_)|[оператор> (multimap)](../standard-library/map-operators.md#operator_gt_)|Проверяет, больше ли объект map или multimap слева от оператора объекта map или multimap справа от оператора.|  
|[оператор>= (map)](../standard-library/map-operators.md#operator_gt__eq)|[оператор>= (multimap)](../standard-library/map-operators.md#operator_gt__eq)|Проверяет, больше или равен объект map или multimap слева от оператора объекту map или multimap справа от оператора.|  
  
### <a name="specialized-template-functions"></a>Специализированные функции шаблонов  
  
|Версия Map|Версия Multimap|Описание|  
|-----------------|----------------------|-----------------|  
|[swap (map)](../standard-library/map-functions.md#swap)|[swap (multimap)](../standard-library/map-functions.md#swap)|Обменивает элементы между двумя объектами map или multimap.|  
  
### <a name="classes"></a>Классы  
  
|||  
|-|-|  
|[Класс value_compare](../standard-library/value-compare-class-map.md)|Предоставляет объект функции, который может сравнить элементы объекта map, сравнивая значения их ключей, чтобы определить их относительный порядок в объекте map.|  
|[Класс map](../standard-library/map-class.md)|Используется для хранения и извлечения данных из коллекции, в которой у каждого элемента есть уникальный ключ, по которым данные автоматически упорядочиваются.|  
|[Класс multimap](../standard-library/multimap-class.md)|Используется для хранения и извлечения данных из коллекции, в которой у каждого элемента есть ключ, по которым данные автоматически упорядочиваются. При этом значения ключей не обязаны быть уникальными.|  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)




