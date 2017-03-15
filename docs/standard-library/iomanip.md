---
title: "&lt;iomanip&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iomanip/std::<iomanip>
- std::<iomanip>
- <iomanip>
- std.<iomanip>
dev_langs:
- C++
helpviewer_keywords:
- iomanip header
ms.assetid: 3681c346-4763-4037-bba4-cf0dc3447974
caps.latest.revision: 21
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 71c6a6f3d9c8c256628f609c6a3e65f6b72df952
ms.lasthandoff: 02/24/2017

---
# <a name="ltiomanipgt"></a>&lt;iomanip&gt;
Включите стандартный заголовок `<iomanip>` объекта `iostreams` для определения нужного числа манипуляторов, каждый из которых принимает один аргумент.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#include <iomanip>  
  
```  
  
## <a name="remarks"></a>Примечания  
 Все эти манипуляторы возвращают неопределенный тип с названиями от **T1** до **T10**, который перегружает как `basic_istream`\<**Elem**, **Tr**>`::`[operator>>](../standard-library/istream-operators.md#operator_gt__gt_), так и `basic_ostream`\<**Elem**, **Tr**>`::`[operator<<](../standard-library/ostream-operators.md#operator_lt__lt_).  
  
### <a name="manipulators"></a>Манипуляторы  
  
|||  
|-|-|  
|[get_money](../standard-library/iomanip-functions.md#iomanip_get_money)|Получает денежную сумму (при необходимости в международном формате).|  
|[get_time](../standard-library/iomanip-functions.md#iomanip_get_time)|Получает время в структуре времени с использованием указанного формата.|  
|[put_money](../standard-library/iomanip-functions.md#iomanip_put_money)|Предоставляет денежную сумму (при необходимости в международном формате).|  
|[put_time](../standard-library/iomanip-functions.md#iomanip_put_time)|Предоставляет время в структуре времени и строку формата, которую следует использовать.|  
|[quoted](../standard-library/iomanip-functions.md#quoted)|Обеспечивает удобное обращение строк с помощью операторов вставки и извлечения.|  
|[resetiosflags](../standard-library/iomanip-functions.md#resetiosflags)|Удаляет указанные флаги.|  
|[setbase](../standard-library/iomanip-functions.md#setbase)|Задает основание целых чисел.|  
|[setfill](../standard-library/iomanip-functions.md#setfill)|Задает символ, который будет использоваться для заполнения пробелов на экране с выравниванием по правому краю.|  
|[setiosflags](../standard-library/iomanip-functions.md#setiosflags)|Задает указанные флаги.|  
|[setprecision](../standard-library/iomanip-functions.md#setprecision)|Задает точность для значений с плавающей запятой.|  
|[setw](../standard-library/iomanip-functions.md#setw)|Задает ширину отображаемого поля.|  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../standard-library/iostream-programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)




