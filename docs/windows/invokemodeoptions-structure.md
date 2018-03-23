---
title: Структура InvokeModeOptions | Документы Microsoft
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::InvokeModeOptions
- event/Microsoft::WRL::InvokeMode
dev_langs:
- C++
helpviewer_keywords:
- InvokeModeOptions structure
- InvokeMode enum
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b27789f582b383530a675da83456a100780760b4
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="invokemodeoptions-structure"></a>Структура InvokeModeOptions

Указывает, следует ли запускать все события в очереди делегата или остановить обработку после возникновения ошибки. Допустимые значения указываются в `InvokeMode` перечисления.

## <a name="syntax"></a>Синтаксис

```
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

[Microsoft::WRL Namespace](../windows/microsoft-wrl-namespace.md)
[Microsoft::WRL::AgileEventSource Class](../windows/agileeventsource-class.md)