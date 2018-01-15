---
title: "SafeAdd | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: SafeAdd
dev_langs: C++
helpviewer_keywords: SafeAdd function
ms.assetid: 3f82b91d-59fe-4ee1-873b-d056182fa8be
caps.latest.revision: "5"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e8b668f5b164934cff6643d73d9b4b6169a9d4b5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="safeadd"></a>SafeAdd
Складывает два числа в виде, обеспечивает защиту от переполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename T, typename U>  
inline bool SafeAdd (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `t`  
 Первое число для добавления. Это должен быть типа T.  
  
 [in] `u`  
 Второе число для сложения. Это должен быть типа u.  
  
 [выходной] `result`  
 Параметр где `SafeAdd` сохраняет результат.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true`При отсутствии ошибок; `false` при возникновении ошибки.  
  
## <a name="remarks"></a>Примечания  
 Этот метод является частью [библиотека SafeInt](../windows/safeint-library.md) и предназначены для одной сложения без создания экземпляра [класс SafeInt](../windows/safeint-class.md).  
  
> [!NOTE]
>  Этот метод использовать только в том случае, когда один математической операции должны быть защищены. При наличии нескольких операций, следует использовать `SafeInt` класса вместо вызова автономного отдельных функций.  
  
 Дополнительные сведения о типах шаблонов T и U см. в разделе [функции SafeInt](../windows/safeint-functions.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** safeint.h  
  
 **Пространство имен:** Microsoft::Utilities  
  
## <a name="see-also"></a>См. также  
 [Функции SafeInt](../windows/safeint-functions.md)   
 [Библиотека SafeInt](../windows/safeint-library.md)   
 [SafeInt-класс](../windows/safeint-class.md)   
 [SafeSubtract](../windows/safesubtract.md)