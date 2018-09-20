---
title: SafeInt::SafeInt | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeInt::SafeInt
- SafeInt
- SafeInt.SafeInt
dev_langs:
- C++
helpviewer_keywords:
- SafeInt class, constructor
ms.assetid: 39e6f632-a396-40e6-9ece-cc3d4c5a78ef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 723dbb3cec2281815c5733b8f2f0fff8f636a3a5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402568"
---
# <a name="safeintsafeint"></a>SafeInt::SafeInt

Создает **SafeInt** объекта.

## <a name="syntax"></a>Синтаксис

```cpp
SafeInt() throw

SafeInt (
   const T& i
) throw ()

SafeInt (
   bool b
) throw ()

template <typename U>
SafeInt (
   const SafeInt <U, E>& u
)

I template <typename U>
SafeInt (
   const U& i
)  
```

### <a name="parameters"></a>Параметры

*i*<br/>
[in] Значение для нового **SafeInt** объекта. Это должен быть параметр типа T или U, в зависимости от конструктора.

*b*<br/>
[in] Логическое значение для нового **SafeInt** объекта.

*u*<br/>
[in] Объект **SafeInt** типа u. Новый **SafeInt** объект будет иметь то же значение, что *u*, но будет иметь тип T.

Тип данных, хранящихся в U **SafeInt**. Это может быть значение типа Boolean, символьного или целочисленного типа. Если это целочисленный тип, он может быть подписанные или не подписанные и находиться в диапазоне от 8 до 64 бит.

## <a name="remarks"></a>Примечания

Дополнительные сведения о типах шаблонов `T` и `E`, см. в разделе [класс SafeInt](../windows/safeint-class.md).

Входной параметр для конструктора *я* или *u*, должно быть логическое значение, символьного или целочисленного типа. Если это другой тип параметра, **SafeInt** вызываемый классом [static_assert](../cpp/static-assert.md) для указания Недопустимый входной параметр.

Конструкторы, использующие тип шаблона `U` автоматически преобразовать входной параметр для типа, заданного параметром `T`. **SafeInt** класс преобразует данные без потери данных. Он выводит в обработчик ошибок `E` если его не удается преобразовать в тип данных `T` без потери данных.

Если вы создаете **SafeInt** из логический параметр, необходимо инициализировать значение немедленно. Не удается сформировать **SafeInt** с помощью кода `SafeInt<bool> sb;`. Это приведет к ошибке компиляции.

## <a name="requirements"></a>Требования

**Заголовок:** safeint.h

**Пространство имен:** msl::utilities

## <a name="see-also"></a>См. также

[Библиотека SafeInt](../windows/safeint-library.md)<br/>
[Класс SafeInt](../windows/safeint-class.md)<br/>
[Класс SafeIntException](../windows/safeintexception-class.md)