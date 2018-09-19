---
title: SafeLessThan | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeLessThan
dev_langs:
- C++
helpviewer_keywords:
- SafeLessThan function
ms.assetid: 9d85bc0d-8d94-4d59-9b72-ef3c63a120a0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 88f734cbcee303741858c933d1c3729720f0e76f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710311"
---
# <a name="safelessthan"></a>SafeLessThan

Определяет, является ли одно число меньше другого.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename T, typename U>
inline bool SafeLessThan (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Параметры

*t*<br/>
[in] Первое число. Это должен быть типа `T`.

*u*<br/>
[in] Второй номер. Это должен быть типа `U`.

## <a name="return-value"></a>Возвращаемое значение

**значение true,** Если *t* — меньше, чем *u*; в противном случае **false**.

## <a name="remarks"></a>Примечания

Этот метод расширяет возможности оператор сравнения стандартные, так как **SafeLessThan** позволяет сравнить две различные виды номер.

Этот метод является частью [библиотека SafeInt](../windows/safeint-library.md) и предназначен для операции одно сравнение, без создания экземпляра [класс SafeInt](../windows/safeint-class.md).

> [!NOTE]
> Этот метод должен использоваться только в тех случаях, когда одной математической операции должны быть защищены. При наличии нескольких операций, следует использовать `SafeInt` класс, вместо того чтобы вызывать отдельные функции автономного.

Дополнительные сведения о типах шаблонов `T` и `U`, см. в разделе [функции SafeInt](../windows/safeint-functions.md).

## <a name="requirements"></a>Требования

**Заголовок:** safeint.h

**Пространство имен:** Microsoft::Utilities

## <a name="see-also"></a>См. также

[Функции SafeInt](../windows/safeint-functions.md)  
[Библиотека SafeInt](../windows/safeint-library.md)  
[Класс SafeInt](../windows/safeint-class.md)  
[SafeLessThanEquals](../windows/safelessthanequals.md)  
[SafeGreaterThan](../windows/safegreaterthan.md)  
[SafeGreaterThanEquals](../windows/safegreaterthanequals.md)