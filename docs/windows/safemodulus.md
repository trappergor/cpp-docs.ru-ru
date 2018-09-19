---
title: SafeModulus | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeModulus
dev_langs:
- C++
helpviewer_keywords:
- SafeModulus function
ms.assetid: ae5c81eb-5dcf-45a5-aa76-465fdfe68654
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b3c1ec84569058b11b20270ea1006bfc438288cf
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717162"
---
# <a name="safemodulus"></a>SafeModulus

Выполняет операцию взятия по модулю на двух чисел.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename T, typename U>
inline bool SafeModulus (
   const T t,
   const U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Параметры

*t*<br/>
[in] Делитель. Это должен быть типа `T`.

*u*<br/>
[in] Делимое. Это должен быть типа `U`.

*результат*<br/>
[out] Параметр где **SafeModulus** сохраняет результат.

## <a name="return-value"></a>Возвращаемое значение

**значение true,** при отсутствии ошибок; **false** при возникновении ошибки.

## <a name="remarks"></a>Примечания

Этот метод является частью [библиотека SafeInt](../windows/safeint-library.md) и предназначен для операции одного модуля, не создавая экземпляр объекта [класс SafeInt](../windows/safeint-class.md).

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
[SafeDivide](../windows/safedivide.md)