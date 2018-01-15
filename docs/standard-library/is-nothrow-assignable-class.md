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
f1_keywords: type_traits/std::is_nothrow_assignable
dev_langs: C++
helpviewer_keywords: is_nothrow_assignable
ms.assetid: aa3aca92-308b-4b1d-b3f3-c54216c48fe7
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fe32798dc98335dbada12e1914a77e89f0d78a25
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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



