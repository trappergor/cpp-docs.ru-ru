---
title: Перечисление FactoryCacheFlags
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::FactoryCacheFlags
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
ms.openlocfilehash: 250c8c8e7ade72bd1a9cd63f0b515774058f0723
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214010"
---
# <a name="factorycacheflags-enumeration"></a>Перечисление FactoryCacheFlags

Определяет, кэшируются ли объекты фабрики.

## <a name="syntax"></a>Синтаксис

```cpp
enum FactoryCacheFlags;
```

## <a name="remarks"></a>Remarks

По умолчанию политика кэширования фабрики указывается как параметр шаблона [ModuleType](moduletype-enumeration.md) при создании объекта [модуля](module-class.md) . Чтобы переопределить эту политику, укажите значение **факторикачефлагс** при создании объекта фабрики.

|||
|-|-|
|`FactoryCacheDefault`|Используется политика кэширования объекта `Module`.|
|`FactoryCacheEnabled`|Включает кэширование фабрики независимо от параметра шаблона `ModuleType`, используемого для создания объекта `Module`.|
|`FactoryCacheDisabled`|Выключает кэширование фабрики независимо от параметра шаблона `ModuleType`, используемого для создания объекта `Module`.|

## <a name="requirements"></a>Требования

**Заголовок:** Implements. h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также раздел

[Пространство имен Microsoft::WRL](microsoft-wrl-namespace.md)
