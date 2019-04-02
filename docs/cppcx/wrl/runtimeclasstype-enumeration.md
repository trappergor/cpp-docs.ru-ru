---
title: RuntimeClassType - перечисление
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassType
helpviewer_keywords:
- RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
ms.openlocfilehash: 3b869be00cdc405569b82bdf3730f8d4ca4f3aab
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58786080"
---
# <a name="runtimeclasstype-enumeration"></a>RuntimeClassType - перечисление

Указывает тип [RuntimeClass](runtimeclass-class.md) экземпляр, который поддерживается.

## <a name="syntax"></a>Синтаксис

```cpp
enum RuntimeClassType;
```

## <a name="members"></a>Участники

### <a name="values"></a>Значения

|name|Описание|
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

[Пространство имен Microsoft::WRL](microsoft-wrl-namespace.md)