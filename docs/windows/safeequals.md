---
title: SafeEquals | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeEquals
dev_langs:
- C++
helpviewer_keywords:
- SafeEquals function
ms.assetid: 6019627d-f170-413b-9abd-2b5b34396a72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 81f30386946c7fd187f1044804b9f1737a94c58f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718660"
---
# <a name="safeequals"></a>SafeEquals

Сравнивает два числа, чтобы определить, равны ли они.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename T, typename U>
inline bool SafeEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Параметры

*t*<br/>
[in] Первое число для сравнения. Это должен быть типа T.

*u*<br/>
[in] Второе число для сравнения. Это должен быть типа u.

## <a name="return-value"></a>Возвращаемое значение

**значение true,** Если *t* и *u* равны; в противном случае **false**.

## <a name="remarks"></a>Примечания

Метод улучшает `==` поскольку **SafeEquals** позволяет сравнить две различных типов чисел.

Этот метод является частью [библиотека SafeInt](../windows/safeint-library.md) и предназначен для операции одно сравнение, без создания экземпляра [класс SafeInt](../windows/safeint-class.md).

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
[SafeNotEquals](../windows/safenotequals.md)