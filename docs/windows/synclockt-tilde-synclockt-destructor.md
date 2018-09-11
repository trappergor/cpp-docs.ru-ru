---
title: 'SyncLockT:: ~ SyncLockT деструктор | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::~SyncLockT
dev_langs:
- C++
helpviewer_keywords:
- ~SyncLockT, destructor
ms.assetid: 9e14870d-017d-45fe-a3dc-cd86b6fa1c3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d75e3e0592d21672397e8d54c565734d53e72614
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599784"
---
# <a name="synclocktsynclockt-destructor"></a>Деструктор SyncLockT::~SyncLockT

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
~SyncLockT();
```

## <a name="remarks"></a>Примечания

Отменяет инициализацию экземпляра **SyncLockT** класса.

Этот деструктор также разблокирует текущего **SyncLockT** экземпляра.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>См. также

[Класс SyncLockT](../windows/synclockt-class.md)