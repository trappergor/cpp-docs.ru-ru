---
title: "Класс is_assignable | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::is_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_assignable
ms.assetid: 53444287-c8be-4ad2-9487-a85c066a4f84
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 3801ef0c7a4642dd3c07b714441e49d7d5ac6bc0
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="isassignable-class"></a>Класс is_assignable
Проверяет, можно ли назначить значение типа `From` типу `To`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class To, class From>  
struct is_assignable;
```  
  
#### <a name="parameters"></a>Параметры  
 Задача  
 Тип объекта, который получает назначение.  
  
 От  
 Тип объекта, который предоставляет значение.  
  
## <a name="remarks"></a>Примечания  
 Невычисленное выражение `declval<To>() = declval<From>()` должно иметь правильный формат. `From` и `To` должны быть полными типами, `void` или массивами с неизвестной границей.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)




