---
title: "Класс is_trivially_assignable | Документы Майкрософт"
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
- is_trivially_assignable
- type_traits/std::is_trivially_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_assignable
ms.assetid: 1284a8f7-4093-426d-9c9a-dabb46f90d6d
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
ms.openlocfilehash: 4b640307631b1407e5309adaa63b39e100839f91
ms.lasthandoff: 02/24/2017

---
# <a name="istriviallyassignable-class"></a>Класс is_trivially_assignable
Проверяет, можно ли значение типа `From` назначить типу `To`  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class To, class From>  
struct is_trivially_assignable;
```  
  
#### <a name="parameters"></a>Параметры  
 Задача  
 Тип объекта, который получает назначение.  
  
 От  
 Тип объекта, который предоставляет значение.  
  
## <a name="remarks"></a>Примечания  
 Выражение `declval<To>() = declval<From>()` должно иметь правильный формат и должно быть известно компилятору как не требующее нетривиальных операций. `From` и `To` должны быть полными типами, `void` или массивами с неизвестной границей.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)




