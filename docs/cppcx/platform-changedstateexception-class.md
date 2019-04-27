---
title: Класс Platform::ChangedStateException
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ChangedStateException
- VCCORLIB/Platform::ChangedStateException::ChangedStateException
helpviewer_keywords:
- Platform::ChangedStateException
ms.assetid: f894beac-9e80-4fac-ac25-89f1dbc0a6a4
ms.openlocfilehash: 79181702c95f8c666b06bdb26319ccb06e55db0a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62161723"
---
# <a name="platformchangedstateexception-class"></a>Класс Platform::ChangedStateException

Создается, если внутреннее состояние объекта было изменено, тем самым делая недействительными результаты метода.

## <a name="syntax"></a>Синтаксис

```cpp
public ref class ChangedStateException : COMException,    IException,    IPrintable,    IEquatable
```

### <a name="remarks"></a>Примечания

Один из примеров ситуаций, когда создается это исключение: метод итератора коллекции или представления коллекции вызван после изменения родительской коллекции, что делает результаты метода недействительными.

Дополнительные сведения см. в описании класса [COMException](../cppcx/platform-comexception-class.md) .

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Метаданные:** platform.winmd

## <a name="see-also"></a>См. также

[Класс Platform::COMException](../cppcx/platform-comexception-class.md)
