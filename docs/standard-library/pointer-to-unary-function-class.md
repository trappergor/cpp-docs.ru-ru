---
title: "Класс pointer_to_unary_function | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xfunctional/std::pointer_to_unary
- pointer_to_unary
dev_langs:
- C++
helpviewer_keywords:
- pointer_to_unary_function function
- pointer_to_unary_function class
ms.assetid: 05600207-b916-4759-beca-6b6facd2d6f6
caps.latest.revision: 21
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
ms.openlocfilehash: 2089886ff915ce9176c883c9dc552f2a45b5c576
ms.contentlocale: ru-ru
ms.lasthandoff: 04/19/2017

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




