---
title: InterfaceList - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceList
helpviewer_keywords:
- InterfaceList structure
ms.assetid: 6ec3228d-eb3e-4b7e-aef1-7dcf17bdf61a
ms.openlocfilehash: 745348e81888b5a87c57fbb99d397fcd423c3ee1
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59025553"
---
# <a name="interfacelist-structure"></a>InterfaceList - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename T, typename U>
struct InterfaceList;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Имя интерфейса; Первый интерфейс в списке рекурсивной.

*U*<br/>
Имя интерфейса; остальные интерфейсы в списке рекурсивной.

## <a name="remarks"></a>Примечания

Используется для создания рекурсивный список интерфейсов.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|name|Описание|
|----------|-----------------|
|`FirstT`|Синоним параметра-шаблона *T*.|
|`RestT`|Синоним параметра-шаблона *U*.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`InterfaceList`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL::Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Details](microsoft-wrl-details-namespace.md)