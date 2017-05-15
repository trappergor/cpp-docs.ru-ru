---
title: "Класс mem_fun1_t | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mem_fun1_t
- xfunctional/std::mem_fun1_t
dev_langs:
- C++
helpviewer_keywords:
- mem_fun1_t class
ms.assetid: 01a8c2c2-b2f7-4e3f-869c-5b5b9f06ea54
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 6f9335afb06b8d07f96dc3d0fc320016a0aad7ab
ms.contentlocale: ru-ru
ms.lasthandoff: 04/19/2017

---
# <a name="memfun1t-class"></a>Класс mem_fun1_t
Класс адаптера, который позволяет вызывать функцию-член **non_const**, принимающую один аргумент, как объект бинарной функции при инициализации с аргументом-указателем.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Result, class Type, class Arg>
class mem_fun1_t : public binary_function<Type *, Arg, Result> {
    explicit mem_fun1_t(
    Result (Type::* _Pm)(Arg));

    Result operator()(
    Type* _Pleft,
    Arg right) const;

 };
```  
  
#### <a name="parameters"></a>Параметры  
 `_Pm`  
 Указатель на функцию-член класса **Type** для преобразования в объект функции.  
  
 `_Pleft`  
 Объект, для которого вызывается функция-член `_Pm`.  
  
 `right`  
 Аргумент, который был передан в `_Pm`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Адаптируемая бинарная функция.  
  
## <a name="remarks"></a>Примечания  
 Класс шаблона сохраняет в частном члене объекта копию `_Pm`, который должен быть указателем на функцию-член класса **тип**. Он определяет свою функцию-член `operator()` как возвращающую ( **_Pleft**->\* `_Pm`)( **right**).  
  
## <a name="example"></a>Пример  
  Конструктор `mem_fun1_t` обычно не используется напрямую; для адаптации функций-членов используется вспомогательная функция `mem_fun`. Пример использования адаптера функции-члена см. в разделе [mem_fun](../standard-library/functional-functions.md#mem_fun).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<functional>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)




