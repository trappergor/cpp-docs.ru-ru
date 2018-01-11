---
title: "&lt;set&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <set>
dev_langs: C++
helpviewer_keywords: set header
ms.assetid: 43cb1ab2-6383-48cf-8bdc-2b96d7203596
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 16338888d64155ddeab188159030ac060ebb2b17
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ltsetgt"></a>&lt;set&gt;
Определяет классы шаблонов контейнеров set и multiset и их вспомогательные шаблоны.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#include <set>  
  
```  
  
## <a name="members"></a>Участники  
  
### <a name="operators"></a>Операторы  
  
|Версия Set|Версия Multiset|Описание:|  
|-----------------|----------------------|-----------------|  
|[operator!= (set)](../standard-library/set-operators.md#op_neq)|[operator!= (multiset)](../standard-library/set-operators.md#op_neq)|Проверяет неравенство объекта set или multiset слева от оператора объекту set или multiset справа от оператора.|  
|[operator< (set)](../standard-library/set-operators.md#op_lt)|[operator< (multiset)](../standard-library/set-operators.md#op_lt_multiset)|Проверяет, меньше ли объект set или multiset слева от оператора объекта set или multiset справа от оператора.|  
|[operator<= (set)](../standard-library/set-operators.md#op_lt_eq)|[operator\<= (multiset)](../standard-library/set-operators.md#op_lt_eq_multiset)|Проверяет, меньше или равен ли объект set или multiset слева от оператора объекту set или multiset справа от оператора.|  
|[operator== (set)](../standard-library/set-operators.md#op_eq_eq)|[operator== (multiset)](../standard-library/set-operators.md#op_eq_eq_multiset)|Проверяет равенство объекта set или multiset слева от оператора объекту set или multiset справа от оператора.|  
|[operator> (set)](../standard-library/set-operators.md#op_gt)|[operator> (multiset)](../standard-library/set-operators.md#op_gt_multiset)|Проверяет, больше ли объект set или multiset слева от оператора объекта set или multiset справа от оператора.|  
|[operator>= (set)](../standard-library/set-operators.md#op_gt_eq)|[operator>= (multiset)](../standard-library/set-operators.md#op_gt_eq_multiset)|Проверяет, больше или равен ли объект set или multiset слева от оператора объекту set или multiset справа от оператора.|  
  
### <a name="specialized-template-functions"></a>Специализированные функции шаблонов  
  
|Версия Set|Версия Multiset|Описание:|  
|-----------------|----------------------|-----------------|  
|[swap](../standard-library/set-functions.md#swap)|[swap (multiset)](../standard-library/set-functions.md#swap_multiset)|Меняет местами элементы двух объектов set или multiset.|  
  
### <a name="classes"></a>Классы  
  
|||  
|-|-|  
|[Класс set](../standard-library/set-class.md)|Используется для хранения и извлечения данных из коллекции, в которой значения элементов должны быть уникальными и в которой они служат в качестве значений ключей, согласно которым данные автоматически упорядочиваются.|  
|[Класс multiset](../standard-library/multiset-class.md)|Используется для хранения и извлечения данных из коллекции, в которой значения элементов не должны быть уникальными и в которой они служат в качестве значений ключей, согласно которым данные автоматически упорядочиваются.|  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)



