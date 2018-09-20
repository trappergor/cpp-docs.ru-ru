---
title: Конструктор SyncLockT::SyncLockT | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockT, constructor
ms.assetid: 713dfd9f-7369-4d86-b4a0-8b32c184d89b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f2d8244b94a308970e87646505cdcade533b717f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376011"
---
# <a name="synclocktsynclockt-constructor"></a>Конструктор SyncLockT::SyncLockT

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
SyncLockT(
   _Inout_ SyncLockT&& other
);

explicit SyncLockT(
   typename SyncTraits::Type sync = SyncTraits::GetInvalidValue()  
);
```

### <a name="parameters"></a>Параметры

*other*<br/>
Ссылка rvalue на другой **SyncLockT** объекта.

*sync*<br/>
Ссылка на другой `SyncLockWithStatusT` объекта.

## <a name="remarks"></a>Примечания

Инициализирует новый экземпляр класса **SyncLockT** класса.

Первый конструктор инициализирует текущий **SyncLockT** из другого объекта **SyncLockT** объекта, указанного параметром *других*и затем недействительными другие  **SyncLockT** объекта. Второй конструктор является **защищенные**и инициализирует текущий **SyncLockT** объекта в недопустимом состоянии.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>См. также

[Класс SyncLockT](../windows/synclockt-class.md)