---
title: ModuleType - перечисление
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ModuleType
helpviewer_keywords:
- ModuleType enumeration
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
ms.openlocfilehash: d822d214d9bad564286cd2c7494c9f480abdcf00
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50524752"
---
# <a name="moduletype-enumeration"></a>ModuleType - перечисление

Указывает, должен ли модуль поддерживать внутрипроцессный или внепроцессный сервер.

## <a name="syntax"></a>Синтаксис

```cpp
enum ModuleType;
```

## <a name="members"></a>Участники

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`InProc`|Внутрипроцессный сервер.|
|`OutOfProc`|Сервер вне процесса.|
|`DisableCaching`|Отключите механизм кэширования для модуля.|
|`InProcDisableCaching`|Сочетание `InProc` и `DisableCaching`.|
|`OutOfProcDisableCaching`|Сочетание `OutOfProc` и `DisableCaching`.|

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)