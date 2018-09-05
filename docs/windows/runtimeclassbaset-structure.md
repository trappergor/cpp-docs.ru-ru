---
title: Структура RuntimeClassBaseT | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT
dev_langs:
- C++
ms.assetid: a62775fb-3359-4f45-9ff1-c07fa8da464b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6ff7af5ceac971bc230addf81dbd7131a455ada1
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43687867"
---
# <a name="runtimeclassbaset-structure"></a>Структура RuntimeClassBaseT

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <
   unsigned int RuntimeClassTypeT
>
friend struct Details::RuntimeClassBaseT;
```

### <a name="parameters"></a>Параметры

*RuntimeClassTypeT*  
Поле флагов, который указывает один или несколько [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) перечислителей.

## <a name="remarks"></a>Примечания

Предоставляет вспомогательные методы для операций `QueryInterface` и получения идентификаторов интерфейсов.

## <a name="members"></a>Участники

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`RuntimeClassBaseT`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)