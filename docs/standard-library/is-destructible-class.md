---
title: "Класс is_destructible | Документы Майкрософт"
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
- type_traits/std::is_destructible
dev_langs:
- C++
helpviewer_keywords:
- is_destructible
ms.assetid: 3bb9b718-1ad5-49ae-93cc-92b93b546b4d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 25574f44995bc118388c3100ee262d9ad13f4f8c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="isdestructible-class"></a>Класс is_destructible
Проверяет, можно ли уничтожить тип.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>  
struct is_destructible;
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Запрашиваемый тип.  
  
## <a name="remarks"></a>Примечания  
 Экземпляр предиката типа имеет значение true, если тип `T` можно уничтожить, в противном случае — значение false. К типам, которые можно уничтожить, относятся ссылочные типы, типы объектов и типы, для которых при типе `U` , равном `remove_all_extents_t<T>` , невычисленный операнд `std::declval<U&>.~U()` имеет правильный формат. Другие типы, включая незавершенные, `void`и типы функций, не являются типами, которые можно уничтожить.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)



