---
title: RuntimeClassType - перечисление
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassType
helpviewer_keywords:
- RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
ms.openlocfilehash: 62a82d5fab9fd22e23a5244d4fda3b7f5202304c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626815"
---
# <a name="runtimeclasstype-enumeration"></a>RuntimeClassType - перечисление

Указывает тип [RuntimeClass](../windows/runtimeclass-class.md) экземпляр, который поддерживается.

## <a name="syntax"></a>Синтаксис

```cpp
enum RuntimeClassType;
```

## <a name="members"></a>Участники

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`ClassicCom`|Классического COM-класс среды выполнения.|
|`Delegate`|Аналогично параметру `ClassicCom`.|
|`InhibitFtmBase`|Отключает `FtmBase` поддержку во время работы `__WRL_CONFIGURATION_LEGACY__` не определен.|
|`InhibitWeakReference`|Отключает поддержку слабых ссылок.|
|`WinRt`|Класс среды выполнения Windows.|
|`WinRtClassicComMix`|Комбинация `WinRt` и `ClassicCom`.|

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)