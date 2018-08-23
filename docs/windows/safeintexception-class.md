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
ms.openlocfilehash: e5996d4e86275dd154e4c6931a55416885929abf
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603665"
---
# <a name="safeintexception-class"></a>Класс SafeIntException

`SafeInt` Класс использует **SafeIntException** чтобы определить, почему не удается выполнить математическую операцию.

## <a name="syntax"></a>Синтаксис

```cpp
class SafeIntException;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

[SafeIntException::SafeIntException](../windows/safeintexception-safeintexception.md)  
Создает **SafeIntException** объекта.

## <a name="remarks"></a>Примечания

[Класс SafeInt](../windows/safeint-class.md) является единственным классом, который использует **SafeIntException** класса.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[Класс SafeIntException](../windows/safeintexception-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** safeint.h

**Пространство имен:** msl::utilities

## <a name="see-also"></a>См. также

[Библиотека SafeInt](../windows/safeint-library.md)  
[Класс SafeInt](../windows/safeint-class.md)