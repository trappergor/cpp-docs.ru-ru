---
title: Структура RuntimeClassFlags | Документация Майкрософт
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassFlags
- implements/Microsoft::WRL::RuntimeClassFlags::value
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::RuntimeClassFlags structure
- Microsoft::WRL::RuntimeClassFlags::value constant
ms.assetid: 7098d605-bd14-4d51-82f4-3def8296a938
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c5bfd9fc6dd87c61149722e8ef7fed79f8f017da
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788842"
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
