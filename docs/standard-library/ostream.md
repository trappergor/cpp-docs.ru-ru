---
title: "&lt;ostream&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- <ostream>
- ostream/std::<ostream>
- std::<ostream>
dev_langs:
- C++
helpviewer_keywords:
- ostream header
ms.assetid: 90c3b6fb-57cd-4ae7-99b8-8512f24a67d2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9ed7238f2c0716f3eaea01bec25ebf54cc24f340
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="ltostreamgt"></a>&lt;ostream&gt;
Определяет класс шаблона [basic_ostream](../standard-library/basic-ostream-class.md), который является посредником при вставке для iostreams. Заголовок также определяет несколько связанных манипуляторов. (Этот заголовок обычно включается автоматически при использовании других заголовков iostream. Его редко приходится включать напрямую.)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#include <ostream>  
  
```  
  
### <a name="typedefs"></a>Определения типов  
  
|||  
|-|-|  
|[ostream](../standard-library/ostream-typedefs.md#ostream)|Создает тип из `basic_ostream`, который специализируется на `char`, и `char_traits`, который специализируется на `char`.|  
|[wostream](../standard-library/ostream-typedefs.md#wostream)|Создает тип из `basic_ostream`, который специализируется на `wchar_t`, и `char_traits`, который специализируется на `wchar_t`.|  
  
### <a name="manipulators"></a>Манипуляторы  
  
|||  
|-|-|  
|[endl](../standard-library/ostream-functions.md#endl)|Завершает строку и очищает буфер.|  
|[ends](../standard-library/ostream-functions.md#ends)|Завершает строку.|  
|[flush](../standard-library/ostream-functions.md#flush)|Очищает буфер.|  
|[swap](../standard-library/ostream-functions.md#swap)|Меняет местами значения левого параметра объекта `basic_ostream` со значениями правого параметра объекта `basic_ostream`.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор<<](../standard-library/ostream-operators.md#op_lt_lt)|Записывает в поток различные типы.|  
  
### <a name="classes"></a>Классы  
  
|||  
|-|-|  
|[basic_ostream](../standard-library/basic-ostream-class.md)|Класс шаблона, который описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока.|  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../standard-library/iostream-programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)



