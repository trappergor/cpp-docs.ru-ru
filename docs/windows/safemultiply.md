---
title: SafeMultiply | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeMultiply
dev_langs:
- C++
helpviewer_keywords:
- SafeMultiply function
ms.assetid: 81d988a5-fac7-4930-8c37-c24fa8e2c853
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9c0c78a8c17c47ea91d89b3dc7451d60ed0a567b
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40019096"
---
# <a name="safemultiply"></a>SafeMultiply
Перемножает два числа вместе способом, который обеспечивает защиту от переполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template<typename T, typename U>  
inline bool SafeMultiply (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *t*  
 Первое число для умножения. Это должен быть типа `T`.  
  
 [in] *u*  
 Второе число для умножения. Это должен быть типа `U`.  
  
 [out] *результат*  
 Параметр где **SafeMultiply** сохраняет результат.  
  
## <a name="return-value"></a>Возвращаемое значение  
 **значение true,** при отсутствии ошибок; **false** при возникновении ошибки.  
  
## <a name="remarks"></a>Примечания  
 Этот метод является частью [библиотека SafeInt](../windows/safeint-library.md) и предназначен для операцию умножения одного без создания экземпляра [класс SafeInt](../windows/safeint-class.md).  
  
> [!NOTE]
>  Этот метод должен использоваться только в тех случаях, когда одной математической операции должны быть защищены. При наличии нескольких операций, следует использовать `SafeInt` класса вместо вызова отдельных автономных функций.  
  
 Дополнительные сведения о типах шаблонов `T` и `U`, см. в разделе [функции SafeInt](../windows/safeint-functions.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** safeint.h  
  
 **Пространство имен:** Microsoft::Utilities  
  
## <a name="see-also"></a>См. также  
 [Функции SafeInt](../windows/safeint-functions.md)   
 [Библиотека SafeInt](../windows/safeint-library.md)   
 [Класс SafeInt](../windows/safeint-class.md)   
 [SafeDivide](../windows/safedivide.md)