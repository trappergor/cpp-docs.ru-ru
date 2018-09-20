---
title: Структура InvokeModeOptions | Документация Майкрософт
ms.custom: ''
ms.date: 03/22/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::InvokeModeOptions
dev_langs:
- C++
helpviewer_keywords:
- InvokeModeOptions structure
- InvokeMode enum
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ea549db29f7fcb67e4d59e341bf7d5ad085b6d7f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392714"
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

[Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)<br/>
[Класс Microsoft::WRL::AgileEventSource](../windows/agileeventsource-class.md)