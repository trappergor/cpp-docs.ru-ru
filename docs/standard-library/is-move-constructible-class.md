---
title: "Класс is_move_constructible | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::is_move_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 15c1fb9b3b4e3dc27b887ac70005be55813399a7
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="ismoveconstructible-class"></a>Класс is_move_constructible
Проверяет, имеет ли тип конструктор перемещения.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>  
struct is_move_constructible;
```  
  
#### <a name="parameters"></a>Параметры  
 T  
 Вычисляемый тип.  
  
## <a name="remarks"></a>Примечания  
 Предикат типа, результатом вычисления которого будет значение true, если тип `T` может быть создан с помощью операции перемещения. Этот предикат эквивалентен `is_constructible<T, T&&>`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)



