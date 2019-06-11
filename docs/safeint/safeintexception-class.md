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
ms.openlocfilehash: 2998bbb83fd568d7ff627d6598c32fb5b17c1e40
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "65515569"
---
# <a name="safeintexception-class"></a>Класс SafeIntException

Класс `SafeInt` использует `SafeIntException` для определения причины, по которой не удается выполнить математическую операцию.

> [!NOTE]
> Последняя версия этой библиотеки размещена здесь: [https://github.com/dcleblanc/SafeInt](https://github.com/dcleblanc/SafeInt).

## <a name="syntax"></a>Синтаксис

```cpp
class SafeIntException;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

name                                                    | Описание
------------------------------------------------------- | ------------------------------------
[SafeIntException::SafeIntException](#safeintexception) | Создает объект `SafeIntException`.

## <a name="remarks"></a>Примечания

[Класс SafeInt](../safeint/safeint-class.md) является единственным классом, который использует класс `SafeIntException`.

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
[in] Значение перечислимых данных, описывающее возникшую ошибку.

### <a name="remarks"></a>Примечания

Возможные значения для параметра *code* определены в файле Safeint.h. Для удобства эти возможные значения также перечислены здесь.

- `SafeIntNoError`
- `SafeIntArithmeticOverflow`
- `SafeIntDivideByZero`
