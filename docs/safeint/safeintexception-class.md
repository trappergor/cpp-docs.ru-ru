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
ms.openlocfilehash: e118d7e3cce47ebb93cef16319a8fc45aab1118b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81349951"
---
# <a name="safeintexception-class"></a>Класс SafeIntException

Класс `SafeInt` использует `SafeIntException` для определения причины, по которой не удается выполнить математическую операцию.

> [!NOTE]
> Последняя версия этой библиотеки [https://github.com/dcleblanc/SafeInt](https://github.com/dcleblanc/SafeInt)находится по адресу .

## <a name="syntax"></a>Синтаксис

```cpp
class SafeIntException;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                                    | Описание
------------------------------------------------------- | ------------------------------------
[SafeIntException::SafeIntException](#safeintexception) | Создает объект `SafeIntException`.

## <a name="remarks"></a>Remarks

[Класс SafeInt](../safeint/safeint-class.md) является единственным классом, который использует класс `SafeIntException`.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`SafeIntException`

## <a name="requirements"></a>Требования

**Заголовок:** safeint.h

**Пространство имен:** msl::utilities

## <a name="safeintexceptionsafeintexception"></a><a name="safeintexception"></a>SafeIntException::SafeIntException

Создает объект `SafeIntException`.

```cpp
SafeIntException();

SafeIntException(
   SafeIntError code
);
```

### <a name="parameters"></a>Параметры

*Код*<br/>
[in] Значение перечислимых данных, описывающее возникшую ошибку.

### <a name="remarks"></a>Remarks

Возможные значения для параметра *code* определены в файле Safeint.h. Для удобства эти возможные значения также перечислены здесь.

- `SafeIntNoError`
- `SafeIntArithmeticOverflow`
- `SafeIntDivideByZero`
