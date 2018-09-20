---
title: Implementshelper-структура | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ImplementsHelper
dev_langs:
- C++
helpviewer_keywords:
- ImplementsHelper structure
ms.assetid: b857ba80-81bd-4e53-92b6-210991954243
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4ff40e03bf464d4c6f434b491c8b48d2b797d72b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440541"
---
# <a name="implementshelper-structure"></a>ImplementsHelper - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <
   typename RuntimeClassFlagsT,
   typename ILst,
   bool IsDelegateToClass
>
friend struct Details::ImplementsHelper;
```

### <a name="parameters"></a>Параметры

*RuntimeClassFlagsT*<br/>
Поле флагов, который указывает один или несколько [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) перечислителей.

*ILst*<br/>
Список идентификаторов интерфейсов.

*IsDelegateToClass*<br/>
Укажите **true** Если текущий экземпляр `Implements` является базовым классом для идентификатор первого интерфейса в *ILst*; в противном случае **false**.

## <a name="remarks"></a>Примечания

Помогает реализовать [реализует](../windows/implements-structure.md) структуры.

Этот шаблон, проходит через список интерфейсов и добавляет их в качестве базовых классов, а также как сведения, необходимые для включения `QueryInterface`.

## <a name="members"></a>Участники

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ImplementsHelper`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)