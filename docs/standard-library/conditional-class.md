---
title: "Класс conditional | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::conditional
dev_langs:
- C++
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 2c764bfc42d633a3036f2e567078b9ea39feea8b
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="conditional-class"></a>Класс conditional
Выделяет один из 2 типов в зависимости от указанного условия.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <bool B, class T1, class T2>  
struct conditional;

template <bool _Test, class _T1, class _T2>  
using conditional_t = typename conditional<_Test, _T1, _T2>::type;
```  
  
#### <a name="parameters"></a>Параметры  
 `B`  
 Значение, определяющее выбранный тип.  
  
 `T1`  
 Результат типа, если B — true.  
  
 `T2`  
 Результат типа, если B — false.  
  
## <a name="remarks"></a>Примечания  
 Член шаблона typedef `conditional<B, T1, T2>::type` равен `T1` , если параметр `B` равен `true`, или `T2` , если параметр `B` равен `false`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)




