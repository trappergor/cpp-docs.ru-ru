---
title: "Класс pointer_to_unary_function | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xfunctional/std::pointer_to_unary
dev_langs:
- C++
helpviewer_keywords:
- pointer_to_unary_function function
- pointer_to_unary_function class
ms.assetid: 05600207-b916-4759-beca-6b6facd2d6f6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 60aba05ea86b27b4ece5eff78ed4c28f8ac39255
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="pointertounaryfunction-class"></a>Класс pointer_to_unary_function
Преобразует указатель на унарную функцию в адаптируемую унарную функцию.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Arg, class Result>
class pointer_to_unary_function
    : public unary_function<Arg, Result>
{
public:
    explicit pointer_to_unary_function(Result(*pfunc)(Arg));
    Result operator()(Arg left) const;
};
```  
  
#### <a name="parameters"></a>Параметры  
 `pfunc`  
 Бинарная функция для преобразования.  
  
 `left`  
 Объект, для которого вызывается функция *\*pfunc*.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Шаблон класса хранит копию **pfunc**. Он определяет свою функцию-член `operator()` как возвращающую ( \* **pfunc**)(_ *Left*).  
  
## <a name="remarks"></a>Примечания  
 Указатель на унарную функцию является объектом функции и может передаваться в любой алгоритм стандартной библиотеки C++, ожидающий унарную функцию в качестве параметра, но не может настраиваться. Для использования его с адаптером, например привязка к нему значения или использование его с negator, он должен быть представлен с вложенными типами **argument_type** и **result_type**, что делает такую настройку возможной. Преобразование посредством `pointer_to_unary_function` позволяет адаптерам функций работать с указателями бинарных функций.  
  
## <a name="example"></a>Пример  
 Конструктор `pointer_to_unary_function` редко используется напрямую. См. раздел по вспомогательной функции [ptr_fun](../standard-library/functional-functions.md#ptr_fun) с примером того, как объявлять и использовать предикат адаптера `pointer_to_unary_function`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<functional>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)



