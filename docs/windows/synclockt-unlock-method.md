---
title: Метод SyncLockT::Unlock | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Unlock method
ms.assetid: e21110a2-03dd-4073-9c3f-73b99e39f405
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f050916f9957531e9275cf76fd3efb6f612cc988
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598856"
---
# <a name="synclocktunlock-method"></a>Метод SyncLockT::Unlock

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
void Unlock();
```

## <a name="remarks"></a>Примечания

Управление ресурсы, удерживаемые текущим **SyncLockT** объекта, если таковые имеются.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>См. также

[Класс SyncLockT](../windows/synclockt-class.md)