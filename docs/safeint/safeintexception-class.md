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
ms.openlocfilehash: 8149a5e1216e26fafc1e0cd4a489cdad0551607c
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615413"
---
# <a name="safeintexception-class"></a>Класс SafeIntException

Класс `SafeInt` использует `SafeIntException` для определения причины, по которой не удается выполнить математическую операцию.

> [!NOTE]
> Последняя версия этой библиотеки находится по адресу [https://github.com/dcleblanc/SafeInt](https://github.com/dcleblanc/SafeInt) .

## <a name="syntax"></a>Синтаксис

```cpp
class SafeIntException;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

name                                                    | Описание
------------------------------------------------------- | ------------------------------------
[SafeIntException:: SafeIntException](#safeintexception) | Создает объект `SafeIntException`.

## <a name="remarks"></a>Комментарии

[Класс SafeInt](safeint-class.md) является единственным классом, который использует класс `SafeIntException`.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`SafeIntException`

## <a name="requirements"></a>Требования

**Заголовок:** safeint.h

**Пространство имен:** msl::utilities

## <a name="safeintexceptionsafeintexception"></a><a name="safeintexception"></a>SafeIntException:: SafeIntException

Создает объект `SafeIntException`.

```cpp
SafeIntException();

SafeIntException(
   SafeIntError code
);
```

### <a name="parameters"></a>Параметры

*code*<br/>
[in] Значение перечислимых данных, описывающее возникшую ошибку.

### <a name="remarks"></a>Комментарии

Возможные значения для параметра *code* определены в файле Safeint.h. Для удобства эти возможные значения также перечислены здесь.

- `SafeIntNoError`
- `SafeIntArithmeticOverflow`
- `SafeIntDivideByZero`
