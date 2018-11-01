---
title: Класс SafeIntException
ms.date: 10/22/2018
ms.topic: reference
f1_keywords:
- SafeIntException Class
- SafeIntException
- SafeIntException.SafeIntException
- SafeIntException::SafeIntException
helpviewer_keywords:
- SafeIntException class
- SafeIntException, constructor
ms.assetid: 88bef958-1f48-4d55-ad4f-d1f9581a293a
ms.openlocfilehash: 80a1573c2f43b1f4b31731083974f87ba389fac2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566664"
---
# <a name="safeintexception-class"></a>Класс SafeIntException

`SafeInt` Класс использует `SafeIntException` чтобы определить, почему не удается выполнить математическую операцию.

> [!NOTE]
> Последнюю версию этой библиотеки находится в [ https://github.com/dcleblanc/SafeInt ](https://github.com/dcleblanc/SafeInt).

## <a name="syntax"></a>Синтаксис

```cpp
class SafeIntException;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                                    | Описание
------------------------------------------------------- | ------------------------------------
[SafeIntException::SafeIntException](#safeintexception) | Создает объект `SafeIntException`.

## <a name="remarks"></a>Примечания

[Класс SafeInt](../windows/safeint-class.md) является единственным классом, который использует `SafeIntException` класса.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`SafeIntException`

## <a name="requirements"></a>Требования

**Заголовок:** safeint.h

**Пространство имен:** msl::utilities

## <a name="safeintexception"></a>SafeIntException::SafeIntException

Создает объект `SafeIntException`.

```cpp
SafeIntException();

SafeIntException(
   SafeIntError code
);
```

### <a name="parameters"></a>Параметры

*код*<br/>
[in] Значение типа перечислимых данных, описывающее возникшую ошибку.

### <a name="remarks"></a>Примечания

Возможные значения *кода* определены в файле Safeint.h. Для удобства возможные значения также перечислены здесь.

- `SafeIntNoError`
- `SafeIntArithmeticOverflow`
- `SafeIntDivideByZero`
