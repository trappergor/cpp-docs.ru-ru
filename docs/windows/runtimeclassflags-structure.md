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
ms.openlocfilehash: 74ae72dc87d45abba04d15303ed2ec92b18f8c28
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668537"
---
# <a name="runtimeclassflags-structure"></a>RuntimeClassFlags - структура

Содержит тип для экземпляра [RuntimeClass](../windows/runtimeclass-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
template <unsigned int flags>
struct RuntimeClassFlags;
```

### <a name="parameters"></a>Параметры

*flags*<br/>
Объект [runtimeclasstype-перечисление](../windows/runtimeclasstype-enumeration.md) значение.

## <a name="members"></a>Участники

### <a name="public-constants"></a>Открытые константы

|name|Описание|
|----------|-----------------|
|[Константа RuntimeClassFlags::value](#value-constant)|Содержит [runtimeclasstype-перечисление](../windows/runtimeclasstype-enumeration.md) значение.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`RuntimeClassFlags`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="value-constant"></a>Константа RuntimeClassFlags::value

Поле, содержащее [runtimeclasstype-перечисление](../windows/runtimeclasstype-enumeration.md) значение.

```cpp
static const unsigned int value = flags;
```
