---
title: "Класс is_nothrow_assignable | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- is_nothrow_assignable
- std.is_nothrow_assignable
- std::is_nothrow_assignable
- type_traits/std::is_nothrow_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_assignable
ms.assetid: aa3aca92-308b-4b1d-b3f3-c54216c48fe7
caps.latest.revision: 13
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 8f7cfa4eafda6061e503b5b8495d64c29a19eda8
ms.lasthandoff: 02/24/2017

---
# <a name="isnothrowassignable-class"></a>Класс is_nothrow_assignable
Проверяет, можно ли значение типа `From` назначить на тип `To` и известно ли назначение как не приводящее к проблемам.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class To, class From>  
struct is_nothrow_assignable;
```  
  
#### <a name="parameters"></a>Параметры  
 Задача  
 Тип объекта, который получает назначение.  
  
 От  
 Тип объекта, который предоставляет значение.  
  
## <a name="remarks"></a>Примечания  
 Выражение `declval<To>() = declval<From>()` должно иметь правильный формат и быть известно компилятору как не вызывающее исключений. `From` и `To` должны быть полными типами, `void` или массивами с неизвестной границей.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)




