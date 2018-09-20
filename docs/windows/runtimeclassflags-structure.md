---
title: Структура RuntimeClassFlags | Документация Майкрософт
ms.custom: ''
ms.date: 09/07/2018
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
ms.openlocfilehash: 39a7684337e7666613bcd824b29417ca5ba0b021
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438058"
---
# <a name="runtimeclassflags-structure"></a>RuntimeClassFlags - структура

Содержит тип для экземпляра [RuntimeClass](../windows/runtimeclass-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
template <
   unsigned int flags
>
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
