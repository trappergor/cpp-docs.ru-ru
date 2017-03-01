---
title: "&lt;set&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.<set>
- std::<set>
- <set>
dev_langs:
- C++
helpviewer_keywords:
- set header
ms.assetid: 43cb1ab2-6383-48cf-8bdc-2b96d7203596
caps.latest.revision: 20
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
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: 1295a8c71464b7cc9d204c807c3492000b73ffa1
ms.lasthandoff: 02/24/2017

---
# <a name="ltsetgt"></a>&lt;set&gt;
Определяет классы шаблонов контейнеров set и multiset и их вспомогательные шаблоны.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#include <set>  
  
```  
  
## <a name="members"></a>Члены  
  
### <a name="operators"></a>Операторы  
  
|Версия Set|Версия Multiset|Описание|  
|-----------------|----------------------|-----------------|  
|[operator!= (set)](../standard-library/set-operators.md#operator_neq)|[operator!= (multiset)](../standard-library/set-operators.md#operator_neq)|Проверяет неравенство объекта set или multiset слева от оператора объекту set или multiset справа от оператора.|  
|[operator< (set)](../standard-library/set-operators.md#operator_lt_)|[operator< (multiset)](../standard-library/set-operators.md#operator_lt_)|Проверяет, меньше ли объект set или multiset слева от оператора объекта set или multiset справа от оператора.|  
|[operator<= (set)](../standard-library/set-operators.md#operator_lt__eq)|[operator\<= (multiset)](../standard-library/set-operators.md#operator_lt__eq)|Проверяет, меньше или равен ли объект set или multiset слева от оператора объекту set или multiset справа от оператора.|  
|[operator== (set)](../standard-library/set-operators.md#operator_eq_eq)|[operator== (multiset)](../standard-library/set-operators.md#operator_eq_eq)|Проверяет равенство объекта set или multiset слева от оператора объекту set или multiset справа от оператора.|  
|[operator> (set)](../standard-library/set-operators.md#operator_gt_)|[operator> (multiset)](../standard-library/set-operators.md#operator_gt_)|Проверяет, больше ли объект set или multiset слева от оператора объекта set или multiset справа от оператора.|  
|[operator>= (set)](../standard-library/set-operators.md#operator_gt__eq)|[operator>= (multiset)](../standard-library/set-operators.md#operator_gt__eq)|Проверяет, больше или равен ли объект set или multiset слева от оператора объекту set или multiset справа от оператора.|  
  
### <a name="specialized-template-functions"></a>Специализированные функции шаблонов  
  
|Версия Set|Версия Multiset|Описание|  
|-----------------|----------------------|-----------------|  
|[swap](../standard-library/set-functions.md#swap)|[swap](../standard-library/set-functions.md#swap)|Меняет местами элементы двух объектов set или multiset.|  
  
### <a name="classes"></a>Классы  
  
|||  
|-|-|  
|[Класс set](../standard-library/set-class.md)|Используется для хранения и извлечения данных из коллекции, в которой значения элементов должны быть уникальными и в которой они служат в качестве значений ключей, согласно которым данные автоматически упорядочиваются.|  
|[Класс multiset](../standard-library/multiset-class.md)|Используется для хранения и извлечения данных из коллекции, в которой значения элементов не должны быть уникальными и в которой они служат в качестве значений ключей, согласно которым данные автоматически упорядочиваются.|  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)




