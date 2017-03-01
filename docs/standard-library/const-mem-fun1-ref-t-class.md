---
title: "Класс const_mem_fun1_ref_t | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::const_mem_fun1_ref_t
- std.const_mem_fun1_ref_t
- xfunctional/std::const_mem_fun1_ref_t
- const_mem_fun1_ref_t
dev_langs:
- C++
helpviewer_keywords:
- const_mem_fun1_ref_t class
ms.assetid: 8220d373-fa1c-44be-a21d-96d49b3ea6bb
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
ms.openlocfilehash: 88dddcd0b43361adc0b06d231f0a6a138999200f
ms.lasthandoff: 02/24/2017

---
# <a name="constmemfun1reft-class"></a>Класс const_mem_fun1_ref_t
Класс адаптера, который позволяет вызывать функцию-член **const**, принимающую один аргумент, как объект бинарной функции при инициализации с ссылочным аргументом.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Result, class Type, class Arg>
class const_mem_fun1_ref_t
 : public binary_function<Type, Arg, Result> 
 {
    explicit const_mem_fun1_ref_t(Result (Type::* Pm)(Arg) const);
    Result operator()(const Type& left, Arg right) const;
 };
```  
  
#### <a name="parameters"></a>Параметры  
 `Pm`  
 Указатель на функцию-член класса **Type** для преобразования в объект функции.  
  
 `left`  
 Объект **const**, для которого вызывается функция-член `Pm`.  
  
 `right`  
 Аргумент, который передается в `Pm`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Адаптируемая бинарная функция.  
  
## <a name="remarks"></a>Примечания  
 Класс шаблона сохраняет в частном члене объекта копию `Pm`, которая должна быть указателем на функцию-член класса **Type**. Он определяет функцию-член `operator()` как возвращающую ( `left`.\* *Pm*)( `right`) **const**.  
  
## <a name="example"></a>Пример  
 Конструктор `const_mem_fun1_ref_t` обычно не используется напрямую; для адаптации функций-членов используется вспомогательная функция `mem_fun_ref`. Примеры использования адаптеров функций-членов см. в разделе [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref_function).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<functional>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)




