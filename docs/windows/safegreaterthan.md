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
ms.openlocfilehash: 8c67dbe68c26a306b59eaf20b741b6b061ac2192
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42596514"
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

[in] *t*  
Первое число для сравнения. Это должен быть типа `T`.

[in] *u*  
Второе число для сравнения. Это должен быть типа `U`.

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

[Функции SafeInt](../windows/safeint-functions.md)  
[Библиотека SafeInt](../windows/safeint-library.md)  
[Класс SafeInt](../windows/safeint-class.md)  
[SafeLessThan](../windows/safelessthan.md)  
[SafeLessThanEquals](../windows/safelessthanequals.md)  
[SafeGreaterThanEquals](../windows/safegreaterthanequals.md)