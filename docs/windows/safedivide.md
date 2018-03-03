---
title: "SafeDivide | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SafeDivide
dev_langs:
- C++
helpviewer_keywords:
- SafeDivide function
ms.assetid: b5b27484-ad6e-46b1-ba9f-1c7120dd103b
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0d6d3b774cb014b8257cf412bf2dec2827abeda2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="safedivide"></a>SafeDivide
Делит два числа в виде, защищает от деления на ноль.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename T, typename U>  
inline bool SafeDivide (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `t`  
 Делитель. Это должен быть типа T.  
  
 [in] `u`  
 Делимое. Это должен быть типа u.  
  
 [выходной] `result`  
 Параметр где `SafeDivide` сохраняет результат.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true`При отсутствии ошибок; `false` при возникновении ошибки.  
  
## <a name="remarks"></a>Примечания  
 Этот метод является частью [библиотека SafeInt](../windows/safeint-library.md) и предназначен для деления одного без создания экземпляра [класс SafeInt](../windows/safeint-class.md).  
  
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
 [SafeModulus](../windows/safemodulus.md)   
 [SafeMultiply](../windows/safemultiply.md)