---
title: SafeDivide | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeDivide
dev_langs:
- C++
helpviewer_keywords:
- SafeDivide function
ms.assetid: b5b27484-ad6e-46b1-ba9f-1c7120dd103b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bd7d581a632158154822f7ce51ac3dc5042b2a48
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42589301"
---
# <a name="safedivide"></a>SafeDivide

Делит два числа, способом, который обеспечивает защиту от деления на ноль.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename T, typename U>
inline bool SafeDivide (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Параметры

[in] *t*  
Делитель. Это должен быть типа T.

[in] *u*  
Делимое. Это должен быть типа u.

[out] *результат*  
Параметр где **SafeDivide** сохраняет результат.

## <a name="return-value"></a>Возвращаемое значение

**значение true,** при отсутствии ошибок; **false** при возникновении ошибки.

## <a name="remarks"></a>Примечания

Этот метод является частью [библиотека SafeInt](../windows/safeint-library.md) и предназначена для одного деления без создания экземпляра [класс SafeInt](../windows/safeint-class.md).

> [!NOTE]
> Этот метод должен использоваться только в тех случаях, когда одной математической операции должны быть защищены. При наличии нескольких операций, следует использовать `SafeInt` класса вместо вызова отдельных автономных функций.

Дополнительные сведения о типах шаблонов T и U см. в разделе [функции SafeInt](../windows/safeint-functions.md).

## <a name="requirements"></a>Требования

**Заголовок:** safeint.h

**Пространство имен:** Microsoft::Utilities

## <a name="see-also"></a>См. также

[Функции SafeInt](../windows/safeint-functions.md)  
[Библиотека SafeInt](../windows/safeint-library.md)  
[Класс SafeInt](../windows/safeint-class.md)  
[SafeModulus](../windows/safemodulus.md)  
[SafeMultiply](../windows/safemultiply.md)