---
title: ModuleType - перечисление
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ModuleType
helpviewer_keywords:
- ModuleType enumeration
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
ms.openlocfilehash: 937649eada481f7c45359fa0816266f62dc03875
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336576"
---
# <a name="moduletype-enumeration"></a>ModuleType - перечисление

Указывает, должен ли модуль поддерживать внутрипроцессный или внепроцессный сервер.

## <a name="syntax"></a>Синтаксис

```cpp
enum ModuleType;
```

## <a name="members"></a>Участники

### <a name="values"></a>Значения

|Имя|Описание:|
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

[Пространство имен Microsoft::WRL](microsoft-wrl-namespace.md)