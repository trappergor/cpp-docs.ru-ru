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
ms.openlocfilehash: 98f37a428c81276788ea4aef315e7266a9da02c4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383406"
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

*t*<br/>
[in] Делитель. Это должен быть типа T.

*u*<br/>
[in] Делимое. Это должен быть типа u.

*результат*<br/>
[out] Параметр где **SafeDivide** сохраняет результат.

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

[Функции SafeInt](../windows/safeint-functions.md)<br/>
[Библиотека SafeInt](../windows/safeint-library.md)<br/>
[Класс SafeInt](../windows/safeint-class.md)<br/>
[SafeModulus](../windows/safemodulus.md)<br/>
[SafeMultiply](../windows/safemultiply.md)