---
title: "noexcept (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: noexcept_cpp
dev_langs: C++
ms.assetid: df24edb9-c6a6-4e37-9914-fd5c0c3716a8
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5068c7cf010c128fd7954ddfd356f49158bf6f17
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="noexcept-c"></a>noexcept (C++)
**C ++ 11:** указывает, может ли функция вызывать исключения.  
  
## <a name="syntax"></a>Синтаксис  
  
> *выражение noexcept*:  
> &nbsp;&nbsp;&nbsp;&nbsp;**noexcept**  
> &nbsp;&nbsp;&nbsp;&nbsp;**noexcept (** *константное выражение* **)**  
  
### <a name="parameters"></a>Параметры  
 *Константное выражение*  
 Константное выражение типа `bool` , представляет ли набор возможных типов исключений не пуст. Безусловная версия эквивалентна `noexcept(true)`.  
  
## <a name="remarks"></a>Примечания  
 Объект *выражение noexcept* представляет собой из *спецификацией исключений*, суффикс к объявлению функции, который представляет набор типов, которые могут соответствовать обработчика исключений для любое исключение, которое завершает работу функция. Унарный оператор условного `noexcept(` *constant_expression* `)` где *constant_expression* yeilds `true`и его синоним безусловный `noexcept`, Укажите, что набор возможных типов исключений, которые можно выйти из функции является пустым. То есть функция никогда не создает исключение и никогда не разрешает исключения распространяться за пределы ее области действия. Оператор `noexcept(` *constant_expression* `)` где *constant_expression* yeilds `false`, или его отсутствие спецификации исключений (отличных от деструктор или освобождение функции), указывает набор возможных исключений, завершившиеся функция набор всех типов.  
 
 Определить функцию как `noexcept` только в том случае, если все функции, которые она вызывает, прямо или косвенно, также являются `noexcept` или `const`. Компилятор не обязательно проверяет каждый путь к коду для исключений, которые могут довести до `noexcept` функции. Если исключение выхода из внешней области функции, помеченной `noexcept`, [std::terminate](../standard-library/exception-functions.md#terminate) вызывается немедленно, и нет никакой гарантии, что будет вызываться деструкторы любых объектов в области видимости. Используйте `noexcept` вместо спецификатора исключения динамических `throw`, который является устаревшим в C ++ 11 и более поздней версии и не полностью реализованы в Visual Studio. Рекомендуем применять `noexcept` на любую функцию, никогда не позволяет исключению распространяться вверх по стеку вызовов. Если функция объявляется `noexcept`, он позволяет компилятору создавать более эффективный код в нескольких разных контекстах.    
  
## <a name="example"></a>Пример  
Функция шаблона, копирующая свой аргумент, может быть объявлена `noexcept` при условии, что копируемым объектом является тип простых старых данных (POD). Такая функция может быть объявлена следующим образом:  
  
```cpp  
#include <type_traits>  
  
template <typename T>  
T copy_object(const T& obj) noexcept(std::is_pod<T>)  
{  
   // ...   
}  
```  
  
## <a name="see-also"></a>См. также  
 [Обработка исключений C++](../cpp/cpp-exception-handling.md) [спецификации исключений (throw, noexcept)](../cpp/exception-specifications-throw-cpp.md)