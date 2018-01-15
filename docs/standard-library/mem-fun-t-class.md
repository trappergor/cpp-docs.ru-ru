---
title: "Класс mem_fun_t | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xfunctional/std::mem_fun_t
dev_langs: C++
helpviewer_keywords: mem_fun_t class
ms.assetid: 242566d4-750c-4c87-9d63-2e2c9d19ca2a
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d78a39fb29ac983c69bf792c4d567c850e697c53
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="memfunt-class"></a>Класс mem_fun_t
Класс адаптера, который позволяет вызывать функцию-член **non_const**, не принимающую аргументы, как объект унарной функции при инициализации с аргументом-указателем.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Result, class Type>
class mem_fun_t : public unary_function<Type *, Result> {
    explicit mem_fun_t(Result (Type::* _Pm)());

    Result operator()(Type* _Pleft) const;

 };
```  
  
#### <a name="parameters"></a>Параметры  
 `_Pm`  
 Указатель на функцию-член класса **Type** для преобразования в объект функции.  
  
 `_Pleft`  
 Объект, для которого вызывается функция-член `_Pm`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Адаптируемая унарная функция.  
  
## <a name="remarks"></a>Примечания  
 Класс шаблона сохраняет в частном члене объекта копию `_Pm`, которая должна быть указателем на функцию-член класса **Type**. В нем определяется функция-член `operator()` как возвращающая returning ( `_Pleft`->* `_Pm`)( ).  
  
## <a name="example"></a>Пример  
 Конструктор `mem_fun_t` обычно не используется напрямую; для адаптации функций-членов используется вспомогательная функция `mem_fun`. Пример использования адаптера функции-члена см. в разделе [mem_fun](../standard-library/functional-functions.md#mem_fun).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<functional>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [\<functional>](../standard-library/functional.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)



