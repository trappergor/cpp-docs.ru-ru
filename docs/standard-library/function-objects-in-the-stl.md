---
title: "Объекты функций в стандартной библиотеке C++ | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- functors
- C++ Standard Library, functors
- C++ Standard Library, function objects
- function objects
ms.assetid: 85f8a735-2c7b-4f10-9c4d-95c666ec4192
caps.latest.revision: 6
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
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 3928493eeb4aa09511b3e58d27383c7a480d06ad
ms.lasthandoff: 02/24/2017

---
# <a name="function-objects-in-the-c-standard-library"></a>Объекты функции в стандартной библиотеке C++
*Объект функции*(или *функтор*) — это любой тип, реализующий operator(). Этот оператор называется *оператором вызова* или иногда *оператором приложения*. Стандартная библиотека C++ использует объекты функций главным образом в качестве критериев сортировки для контейнеров и в алгоритмах.  
  
 Объекты функций обеспечивают два основных преимущества по сравнению с прямым вызовом функций. Во-первых, объект функции может содержать состояние. Во-вторых, объект функции является типом и поэтому может использоваться в качестве параметра шаблона.  
  
## <a name="creating-a-function-object"></a>Создание объекта функции  
 Чтобы создать объект функции, создайте тип и реализуйте operator(), например:  
  
Функтор class  
   {  
   public:  
   int operator()(int a, int b)  
   {  
   return a <b;  
   }  
   };  
  
 Последняя строка функции `main` демонстрирует способ вызов объекта функции. Этот вызов выглядит как вызов функции, но в действительности это вызов оператора operator() типа Functor. Сходство между вызовом объекта функции и вызовом функции заключается в том, как появляется термин "объект функции".  
  
## <a name="function-objects-and-containers"></a>Объекты функций и контейнеры  
 Стандартная библиотека C++ содержит несколько объектов функций в файле заголовка [\<functional>](../standard-library/functional.md). Один из этих объектов функций применяется как критерий сортировки для контейнеров. Например, контейнер `set` объявляется следующим образом:  
  
```  
template <class Key,  
    class Traits=less<Key>,  
    class Allocator=allocator<Key>>  
class set  
```  
  
 Второй аргумент шаблона — объект функции `less`. Этот объект функции возвращает значение `true` , если переданный ему первый параметр меньше, чем второй параметр. Поскольку некоторые контейнеры сортируют свои элементы, контейнеру требуется способ сравнения двух элементов, и это выполняется с помощью объекта функции. Можно определить собственные критерии сортировки для контейнеров, создав объект функции и указав его в списке шаблонов для контейнера.  
  
## <a name="function-objects-and-algorithms"></a>Объекты функций и алгоритмы  
 Объекты функций также используются в алгоритмах. Например, алгоритм `remove_if` объявляется следующим образом:  
  
```  
template <class ForwardIterator, class Predicate>  
ForwardIterator remove_if(
    ForwardIterator first,  
    ForwardIterator last,  
    Predicate pred);
```  
  
 Последний аргумент `remove_if` является объектом функции, который возвращает логическое значение ( *предикат*). Если результат выполнения объекта функции — значение `true`, элемент удаляется из контейнера, доступ к которому получают итераторы ` first` и ` last`. Можно использовать любые объекты функций, объявленные в заголовке [\<functional>](../standard-library/functional.md) для аргумента ` pred`, или создать свой собственный.  
  
## <a name="see-also"></a>См. также  
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)


