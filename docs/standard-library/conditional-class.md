---
title: "Класс conditional | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::conditional
dev_langs:
- C++
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4c0c6deb6a7167852101efba30a978aee78f96f9
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
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



