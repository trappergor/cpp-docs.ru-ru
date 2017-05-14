---
title: "Класс mem_fun_ref_t | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xfunctional/std::mem_fun_ref_t
- mem_fun_ref_t
dev_langs:
- C++
helpviewer_keywords:
- mem_fun_ref_t class
ms.assetid: 7dadcac3-8d33-4e4b-a792-81bd53d3df39
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
ms.openlocfilehash: a462fa28f086f2ff0f74e35594dbd651e6d416d9
ms.contentlocale: ru-ru
ms.lasthandoff: 04/19/2017

---
# <a name="memfunreft-class"></a>Класс mem_fun_ref_t
Класс адаптера, который позволяет вызывать функцию-член **non_const**, не принимающую аргументы, как объект унарной функции при инициализации с ссылочным аргументом.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Result, class Type>
class mem_fun_ref_t : public unary_function<Type, Result> {
    explicit mem_fun_ref_t(
    Result (Type::* _Pm)());

    Result operator()(Type& left) const;

 };
```  
  
#### <a name="parameters"></a>Параметры  
 `_Pm`  
 Указатель на функцию-член класса **Type** для преобразования в объект функции.  
  
 `left`  
 Объект, для которого вызывается функция-член `_Pm`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Адаптируемая унарная функция.  
  
## <a name="remarks"></a>Примечания  
 Класс шаблона сохраняет в частном члене объекта копию `_Pm`, который должен быть указателем на функцию-член класса **тип**. Он определяет свою функцию-член `operator()` как возвращающую ( **left**.* `_Pm`)( ).  
  
## <a name="example"></a>Пример  
  Конструктор `mem_fun_ref_t` обычно не используется напрямую; для адаптации функций-членов используется вспомогательная функция `mem_fun_ref`. Пример использования адаптеров функций-членов см. в разделе [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<functional>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)




