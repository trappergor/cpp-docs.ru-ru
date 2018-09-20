---
title: Класс SafeIntException | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeIntException Class
dev_langs:
- C++
helpviewer_keywords:
- SafeIntException class
ms.assetid: 88bef958-1f48-4d55-ad4f-d1f9581a293a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0a0eda94c370f978bd04d7c2de1dd3e06237e490
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46437720"
---
# <a name="safeintexception-class"></a>Класс SafeIntException

`SafeInt` Класс использует **SafeIntException** чтобы определить, почему не удается выполнить математическую операцию.

## <a name="syntax"></a>Синтаксис

```cpp
class SafeIntException;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

[SafeIntException::SafeIntException](../windows/safeintexception-safeintexception.md)<br/>
Создает **SafeIntException** объекта.

## <a name="remarks"></a>Примечания

[Класс SafeInt](../windows/safeint-class.md) является единственным классом, который использует **SafeIntException** класса.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[Класс SafeIntException](../windows/safeintexception-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** safeint.h

**Пространство имен:** msl::utilities

## <a name="see-also"></a>См. также

[Библиотека SafeInt](../windows/safeint-library.md)<br/>
[Класс SafeInt](../windows/safeint-class.md)