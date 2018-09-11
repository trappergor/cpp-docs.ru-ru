---
title: SafeAdd | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeAdd
dev_langs:
- C++
helpviewer_keywords:
- SafeAdd function
ms.assetid: 3f82b91d-59fe-4ee1-873b-d056182fa8be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7e84b76f8079656da3ed19aa2c690bf240854015
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42594360"
---
# <a name="safeadd"></a>SafeAdd

Складывает два числа способом, который обеспечивает защиту от переполнения.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename T, typename U>
inline bool SafeAdd (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Параметры

[in] *t*  
Первое число для добавления. Это должен быть типа T.

[in] *u*  
Второе число для добавления. Это должен быть типа u.

[out] *результат*  
Параметр где **SafeAdd** сохраняет результат.

## <a name="return-value"></a>Возвращаемое значение

**значение true,** при отсутствии ошибок; **false** при возникновении ошибки.

## <a name="remarks"></a>Примечания

Этот метод является частью [библиотека SafeInt](../windows/safeint-library.md) и предназначен для операции одно добавление без создания экземпляра [класс SafeInt](../windows/safeint-class.md).

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
[SafeSubtract](../windows/safesubtract.md)