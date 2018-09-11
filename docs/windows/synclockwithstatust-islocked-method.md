---
title: Метод SyncLockWithStatusT::IsLocked | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked
dev_langs:
- C++
helpviewer_keywords:
- IsLocked method
ms.assetid: e1b75b7b-c145-471a-aa5d-71abf31f5990
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d70a2c316f9e7994292f3dc29cef5bce993778ad
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595067"
---
# <a name="synclockwithstatustislocked-method"></a>Метод SyncLockWithStatusT::IsLocked

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
bool IsLocked() const;
```

## <a name="remarks"></a>Примечания

Указывает ли текущий **SyncLockWithStatusT** объекта, которому принадлежит ресурс, то есть, **SyncLockWithStatusT** объект *заблокирован*.

## <a name="return-value"></a>Возвращаемое значение

**значение true,** Если **SyncLockWithStatusT** объектов заблокирован; в противном случае — значение **false**.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>См. также

[Класс SyncLockWithStatusT](../windows/synclockwithstatust-class.md)