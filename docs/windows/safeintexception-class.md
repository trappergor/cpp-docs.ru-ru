---
title: Класс SafeIntException | Документация Майкрософт
ms.custom: ''
ms.date: 09/27/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeIntException Class
- SafeIntException
- SafeIntException.SafeIntException
- SafeIntException::SafeIntException
dev_langs:
- C++
helpviewer_keywords:
- SafeIntException class
- SafeIntException, constructor
ms.assetid: 88bef958-1f48-4d55-ad4f-d1f9581a293a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4ffd82f80b8af0b53ca86ca3daded84580e1e07b
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235741"
---
# <a name="safeintexception-class"></a>Класс SafeIntException

`SafeInt` Класс использует `SafeIntException` чтобы определить, почему не удается выполнить математическую операцию.

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

*Код*<br/>
[in] Значение типа перечислимых данных, описывающее возникшую ошибку.

### <a name="remarks"></a>Примечания

Возможные значения *кода* определены в файле Safeint.h. Для удобства возможные значения также перечислены здесь.

- `SafeIntNoError`
- `SafeIntArithmeticOverflow`
- `SafeIntDivideByZero`
