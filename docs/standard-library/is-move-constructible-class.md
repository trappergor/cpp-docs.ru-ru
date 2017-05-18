---
title: "Класс is_move_constructible | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_move_constructible
- type_traits/std::is_move_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
caps.latest.revision: 12
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: 91f451ef7ec496791d6a1a8d28965dbb5b684584
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

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




