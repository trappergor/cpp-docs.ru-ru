---
title: SafeIntException::SafeIntException | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeIntException
- SafeIntException.SafeIntException
- SafeIntException::SafeIntException
dev_langs:
- C++
helpviewer_keywords:
- SafeIntException, constructor
ms.assetid: 8e5a0c24-a56b-4c80-9ee8-876604b1e7dc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 749ef965520732c37457613f44e0a23e213023db
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700977"
---
# <a name="safeintexceptionsafeintexception"></a>SafeIntException::SafeIntException

Создает **SafeIntException** объекта.

## <a name="syntax"></a>Синтаксис

```cpp
SafeIntException();

SafeIntException(
   SafeIntError code
);
```

### <a name="parameters"></a>Параметры

*Код*<br/>
[in] Значение типа перечислимых данных, описывающее возникшую ошибку.

## <a name="remarks"></a>Примечания

Возможные значения *кода* определены в файле Safeint.h. Для удобства возможные значения также перечислены здесь.

- `SafeIntNoError`

- `SafeIntArithmeticOverflow`

- `SafeIntDivideByZero`

## <a name="requirements"></a>Требования

**Заголовок:** safeint.h

**Пространство имен:** msl::utilities

## <a name="see-also"></a>См. также

[Библиотека SafeInt](../windows/safeint-library.md)  
[Класс SafeIntException](../windows/safeintexception-class.md)  
[Класс SafeInt](../windows/safeint-class.md)