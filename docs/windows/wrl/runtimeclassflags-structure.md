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
ms.openlocfilehash: 4cbd3f367bc57c2eedf672422a458b67b1908fc0
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336751"
---
# <a name="runtimeclassflags-structure"></a>RuntimeClassFlags - структура

Содержит тип для экземпляра [RuntimeClass](runtimeclass-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
template <unsigned int flags>
struct RuntimeClassFlags;
```

### <a name="parameters"></a>Параметры

*flags*<br/>
Объект [runtimeclasstype-перечисление](runtimeclasstype-enumeration.md) значение.

## <a name="members"></a>Участники

### <a name="public-constants"></a>Открытые константы

|name|Описание:|
|----------|-----------------|
|[Константа RuntimeClassFlags::value](#value-constant)|Содержит [runtimeclasstype-перечисление](runtimeclasstype-enumeration.md) значение.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`RuntimeClassFlags`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="value-constant"></a>Константа RuntimeClassFlags::value

Поле, содержащее [runtimeclasstype-перечисление](runtimeclasstype-enumeration.md) значение.

```cpp
static const unsigned int value = flags;
```
