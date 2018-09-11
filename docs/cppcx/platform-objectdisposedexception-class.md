---
title: Класс Platform::ObjectDisposedException | Документация Майкрософт
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ObjectDisposedException
- VCCORLIB/Platform::ObjectDisposedException::ObjectDisposedException
dev_langs:
- C++
helpviewer_keywords:
- Platform::ObjectDisposedException
ms.assetid: 68506fe4-d09c-4407-999f-1e3edb261d41
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6f0574885fb404572052fbf5066b522ed0208eba
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44106929"
---
# <a name="platformobjectdisposedexception-class"></a>Класс Platform::ObjectDisposedException

Вызывается при выполнении операции над ликвидированным объектом.

## <a name="syntax"></a>Синтаксис

```cpp
public ref class ObjectDisposedException : COMException,    IException,    IPrintable,    IEquatable
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в описании класса [COMException](../cppcx/platform-comexception-class.md).

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Метаданные:** platform.winmd

## <a name="see-also"></a>См. также

[Класс Platform::COMException](../cppcx/platform-comexception-class.md)