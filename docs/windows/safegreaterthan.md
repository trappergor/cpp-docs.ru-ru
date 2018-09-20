---
title: SafeGreaterThan | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeGreaterThan
dev_langs:
- C++
helpviewer_keywords:
- SafeGreaterThan function
ms.assetid: 32cecac9-ba88-43eb-a7a4-30e390456739
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eab7af0a5a72c8f5b08e046a527026e77ca67dea
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411480"
---
# <a name="safegreaterthan"></a>SafeGreaterThan

Сравнивает два числа.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename T, typename U>
inline bool SafeGreaterThan (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Параметры

*t*<br/>
[in] Первое число для сравнения. Это должен быть типа `T`.

*u*<br/>
[in] Второе число для сравнения. Это должен быть типа `U`.

## <a name="return-value"></a>Возвращаемое значение

**значение true,** Если *t* больше, чем *u*; в противном случае **false**.

## <a name="remarks"></a>Примечания

**SafeGreaterThan** расширяет оператор сравнения регулярного, используя для сравнения двух различных типов чисел.

Этот метод является частью [библиотека SafeInt](../windows/safeint-library.md) и предназначен для операции одно сравнение, без создания экземпляра [класс SafeInt](../windows/safeint-class.md).

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
[SafeLessThan](../windows/safelessthan.md)<br/>
[SafeLessThanEquals](../windows/safelessthanequals.md)<br/>
[SafeGreaterThanEquals](../windows/safegreaterthanequals.md)