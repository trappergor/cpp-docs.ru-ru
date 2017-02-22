---
title: "&lt; tuple &gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<tuple>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tuple - заголовок [TR1]"
ms.assetid: e4ef5c2d-318b-44f6-8bce-fce4ecd796a3
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# &lt; tuple &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет шаблон `tuple` экземпляры которых содержат объекты различных типов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#include <tuple>  
```  
  
### <a name="classes"></a>Классы  
  
|||  
|-|-|  
|[кортеж](../standard-library/tuple-class.md)|Создает оболочку для фиксированной длины последовательности элементов.|  
|[Класс tuple_element](../standard-library/tuple-element-class-tuple.md)|Заключает в оболочку тип элемента `tuple`.|  
|[Класс tuple_size](../standard-library/tuple-size-class-tuple.md)|Создает оболочку для счетчика элементов `tuple`.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор ==](../Topic/%3Ctuple%3E%20operators.md#operator_eq_eq)|Сравнение `tuple` объекты, равно|  
|[оператор! =](../Topic/%3Ctuple%3E%20operators.md#operator_neq)|Сравнение `tuple` объекты, не равно|  
|[оператор <](../Topic/%3Ctuple%3E%20operators.md#operator_lt_)|Сравнение `tuple` объекты, меньше, чем|  
|[оператор < =](../Topic/%3Ctuple%3E%20operators.md#operator_lt__eq)|Сравнение `tuple` объекты, меньше или равно|  
|[оператор >](../Topic/%3Ctuple%3E%20operators.md#operator_gt_)|Сравнение `tuple` больше объектов|  
|[оператор > =](../Topic/%3Ctuple%3E%20operators.md#operator_gt__eq)|Сравнение `tuple` объектов, больше или равно|  
  
### <a name="functions"></a>Функции  
  
|||  
|-|-|  
|[Получить](../Topic/%3Ctuple%3E%20functions.md#get_function)|Возвращает элемент из объекта `tuple`.|  
|[make_tuple](../Topic/%3Ctuple%3E%20functions.md#make_tuple_function)|Делает `tuple` из значения элемента.|  
|[связать](../Topic/%3Ctuple%3E%20functions.md#tie_function)|Делает `tuple` из ссылки на элемент.|  
  
## <a name="see-also"></a>См. также  
 [\< массива>](../standard-library/array.md)

