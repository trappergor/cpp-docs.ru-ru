---
title: RuntimeClassType - перечисление
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassType
helpviewer_keywords:
- RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
ms.openlocfilehash: 80e8a120f7e3666721ff839a2a696388a64d734e
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59035962"
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