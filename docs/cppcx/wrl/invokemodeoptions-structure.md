---
title: Структура InvokeModeOptions
ms.date: 03/22/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::InvokeModeOptions
helpviewer_keywords:
- InvokeModeOptions structure
- InvokeMode enum
ms.openlocfilehash: 0e5b45042c9959b87ad5db97ab755e49de469149
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59035284"
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