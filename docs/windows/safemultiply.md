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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c0eb1b8b37737d1c0c36af28da9b0c656e26de7d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396754"
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

*t*<br/>
[in] Первое число для перемножения. Это должен быть типа `T`.

*u*<br/>
[in] Второе число для перемножения. Это должен быть типа `U`.

*результат*<br/>
[out] Параметр где **SafeMultiply** сохраняет результат.

## <a name="return-value"></a>Возвращаемое значение

**значение true,** при отсутствии ошибок; **false** при возникновении ошибки.

## <a name="remarks"></a>Примечания

Этот метод является частью [библиотека SafeInt](../windows/safeint-library.md) и предназначен для операцию умножения одного без создания экземпляра [класс SafeInt](../windows/safeint-class.md).

> [!NOTE]
> Этот метод должен использоваться только в тех случаях, когда одной математической операции должны быть защищены. При наличии нескольких операций, следует использовать `SafeInt` класса вместо вызова отдельных автономных функций.

Дополнительные сведения о типах шаблонов `T` и `U`, см. в разделе [функции SafeInt](../windows/safeint-functions.md).

## <a name="requirements"></a>Требования

**Заголовок:** safeint.h

**Пространство имен:** Microsoft::Utilities

## <a name="see-also"></a>См. также

[Функции SafeInt](../windows/safeint-functions.md)<br/>
[Библиотека SafeInt](../windows/safeint-library.md)<br/>
[Класс SafeInt](../windows/safeint-class.md)<br/>
[SafeDivide](../windows/safedivide.md)