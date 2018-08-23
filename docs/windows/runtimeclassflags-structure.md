---
title: Структура RuntimeClassFlags | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassFlags
dev_langs:
- C++
helpviewer_keywords:
- RuntimeClassFlags structure
ms.assetid: 7098d605-bd14-4d51-82f4-3def8296a938
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f0a32fc373900af1a4322f4f2511c44417d2916a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42594278"
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

*flags*  
Объект [runtimeclasstype-перечисление](../windows/runtimeclasstype-enumeration.md) значение.

## <a name="members"></a>Участники

### <a name="public-constants"></a>Открытые константы

|name|Описание:|
|----------|-----------------|
|[Константа RuntimeClassFlags::value](../windows/runtimeclassflags-value-constant.md)|Содержит [runtimeclasstype-перечисление](../windows/runtimeclasstype-enumeration.md) значение.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`RuntimeClassFlags`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)