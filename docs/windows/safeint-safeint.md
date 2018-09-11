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
ms.openlocfilehash: 2ddb7092b1a5556485848d122e21ac54b6efe182
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42606959"
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

[in] *я*  
Значение для нового **SafeInt** объекта. Это должен быть параметр типа T или U, в зависимости от конструктора.

[in] *b*  
Логическое значение для нового **SafeInt** объекта.

[in] *u*  
Объект **SafeInt** типа u. Новый **SafeInt** объект будет иметь то же значение, что *u*, но будет иметь тип T.

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

[Библиотека SafeInt](../windows/safeint-library.md)  
[Класс SafeInt](../windows/safeint-class.md)  
[Класс SafeIntException](../windows/safeintexception-class.md)