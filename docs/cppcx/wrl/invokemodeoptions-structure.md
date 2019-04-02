---
title: Структура InvokeModeOptions
ms.date: 03/22/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::InvokeModeOptions
helpviewer_keywords:
- InvokeModeOptions structure
- InvokeMode enum
ms.openlocfilehash: ff16c6c5a2ce09313283198fe0b86e95d572e46c
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785973"
---
# <a name="invokemodeoptions-structure"></a>Структура InvokeModeOptions

Указывает, следует ли запускать все события в очереди делегат, для остановки обработки после возникновения ошибки. Допустимые значения указываются в `InvokeMode` перечисления.

## <a name="syntax"></a>Синтаксис

```cpp
enum InvokeMode
{
   StopOnFirstError = 1,
   FireAll = 2,
};

struct InvokeModeOptions
{
   static const InvokeMode invokeMode = invokeModeValue;
};
```

## <a name="requirements"></a>Требования

**Заголовок:** event.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](microsoft-wrl-namespace.md)<br/>
[Класс Microsoft::WRL::AgileEventSource](agileeventsource-class.md)