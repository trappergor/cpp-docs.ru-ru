---
title: Класс Platform::AccessDeniedException
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::AccessDeniedException
- VCCORLIB/Platform::AccessDeniedException::AccessDeniedException
helpviewer_keywords:
- Platform::AccessDeniedException
ms.assetid: 6ae2155b-7b16-4587-8d2d-da05eab4c7e9
ms.openlocfilehash: 4865492e3b5d8e4acc35e58081a226c9e66ed99f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50588153"
---
# <a name="platformaccessdeniedexception-class"></a>Класс Platform::AccessDeniedException

Возникает при запрете доступа к ресурсу или функции.

## <a name="syntax"></a>Синтаксис

```cpp
public ref class AccessDeniedException : COMException,    IException,    IPrintable,   IEquatable
```

### <a name="remarks"></a>Примечания

Если возникло это исключение, проверьте, что вы запросили соответствующую возможность и указали необходимые объявления в манифесте пакета приложения. Дополнительные сведения см. в статье [COMException](../cppcx/platform-comexception-class.md) .

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Метаданные:** platform.winmd

## <a name="see-also"></a>См. также

[Класс Platform::COMException](../cppcx/platform-comexception-class.md)