---
title: "SafeSubtract | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SafeSubtract
dev_langs:
- C++
helpviewer_keywords:
- SafeSubtract function
ms.assetid: c2712ddc-173f-46a1-b09c-e7ebbd9e68b2
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5b94d84e6a348b68258fc1b57c2e0ad9ad30e36d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="safesubtract"></a>SafeSubtract
Вычитает два числа в способом, который обеспечивает защиту от переполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename T, typename U>  
inline bool SafeSubtract (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `t`  
 Первое число операции вычитания. Это должен быть типа T.  
  
 [in] `u`  
 Вычитаемое число `t`. Это должен быть типа u.  
  
 [выходной] `result`  
 Параметр где `SafeSubtract` сохраняет результат.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true`При отсутствии ошибок; `false` при возникновении ошибки.  
  
## <a name="remarks"></a>Примечания  
 Этот метод является частью [библиотека SafeInt](../windows/safeint-library.md) и предназначен для выполнения операции вычитания одного без создания экземпляра [класс SafeInt](../windows/safeint-class.md).  
  
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
 [SafeAdd](../windows/safeadd.md)