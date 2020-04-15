---
title: RuntimeClassFlags - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassFlags
- implements/Microsoft::WRL::RuntimeClassFlags::value
helpviewer_keywords:
- Microsoft::WRL::RuntimeClassFlags structure
- Microsoft::WRL::RuntimeClassFlags::value constant
ms.assetid: 7098d605-bd14-4d51-82f4-3def8296a938
ms.openlocfilehash: 9fed5bb31b077288495a78aefcbd8401b3520bb6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367224"
---
# <a name="runtimeclassflags-structure"></a>RuntimeClassFlags - структура

Содержит тип для экземпляра [RuntimeClass](runtimeclass-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
template <unsigned int flags>
struct RuntimeClassFlags;
```

### <a name="parameters"></a>Параметры

*Флаги*<br/>
Значение [значения runtimeClassType.](runtimeclasstype-enumeration.md)

## <a name="members"></a>Участники

### <a name="public-constants"></a>Открытые константы

|Имя|Описание|
|----------|-----------------|
|[Константа RuntimeClassFlags::value](#value-constant)|Содержит значение [enumeration RuntimeClassType.](runtimeclasstype-enumeration.md)|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`RuntimeClassFlags`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="runtimeclassflagsvalue-constant"></a><a name="value-constant"></a>RuntimeClassFlags::value Constant

Поле, содержащее значение [значения значения значения runtimeClassType Enumeration.](runtimeclasstype-enumeration.md)

```cpp
static const unsigned int value = flags;
```
