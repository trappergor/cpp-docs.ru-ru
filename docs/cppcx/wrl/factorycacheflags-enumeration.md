---
title: Перечисление FactoryCacheFlags
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::FactoryCacheFlags
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
ms.openlocfilehash: 8cf4af2ac0b4557fc6b175b84c47f83dd8a6e4ba
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59037449"
---
# <a name="factorycacheflags-enumeration"></a>Перечисление FactoryCacheFlags

Определяет, кэшируются ли объекты фабрики.

## <a name="syntax"></a>Синтаксис

```cpp
enum FactoryCacheFlags;
```

## <a name="remarks"></a>Примечания

По умолчанию политика кэширования указывается как [ModuleType](moduletype-enumeration.md) параметр шаблона при создании [модуль](module-class.md) объекта. Чтобы переопределить эту политику, укажите **FactoryCacheFlags** значение при создании объекта фабрики.

|||
|-|-|
|`FactoryCacheDefault`|Используется политика кэширования объекта `Module`.|
|`FactoryCacheEnabled`|Включает кэширование фабрики независимо от параметра шаблона `ModuleType`, используемого для создания объекта `Module`.|
|`FactoryCacheDisabled`|Выключает кэширование фабрики независимо от параметра шаблона `ModuleType`, используемого для создания объекта `Module`.|

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](microsoft-wrl-namespace.md)