---
title: Interfacelist-структура | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceList
dev_langs:
- C++
helpviewer_keywords:
- InterfaceList structure
ms.assetid: 6ec3228d-eb3e-4b7e-aef1-7dcf17bdf61a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 61a8e7b36448a485705b914fbb37892271d7d9fc
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42597170"
---
# <a name="interfacelist-structure"></a>InterfaceList - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <
   typename T,
   typename U
>
struct InterfaceList;
```

### <a name="parameters"></a>Параметры

*T*  
Имя интерфейса; Первый интерфейс в списке рекурсивной.

*U*  
Имя интерфейса; остальные интерфейсы в списке рекурсивной.

## <a name="remarks"></a>Примечания

Используется для создания рекурсивный список интерфейсов.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание:|
|----------|-----------------|
|`FirstT`|Синоним параметра-шаблона *T*.|
|`RestT`|Синоним параметра-шаблона *U*.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`InterfaceList`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)