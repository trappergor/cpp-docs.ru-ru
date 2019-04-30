---
title: ModuleType - перечисление
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ModuleType
helpviewer_keywords:
- ModuleType enumeration
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
ms.openlocfilehash: 3c7486cbc761975dd133f229f23dcf0b70e7e3ac
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403234"
---
# <a name="moduletype-enumeration"></a>ModuleType - перечисление

Указывает, должен ли модуль поддерживать внутрипроцессный или внепроцессный сервер.

## <a name="syntax"></a>Синтаксис

```cpp
enum ModuleType;
```

## <a name="members"></a>Участники

### <a name="values"></a>Значения

|name|Описание|
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