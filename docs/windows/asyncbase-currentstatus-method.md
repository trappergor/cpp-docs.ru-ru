---
title: Метод AsyncBase::CurrentStatus | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::CurrentStatus
dev_langs:
- C++
helpviewer_keywords:
- CurrentStatus method
ms.assetid: 26ee4c4a-6525-4a5f-b49c-3ca40c365eb6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 792f9f6c6d76097459498c43068f46d86b2e2349
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401489"
---
# <a name="asyncbasecurrentstatus-method"></a>Метод AsyncBase::CurrentStatus

Извлекает состояние текущей асинхронной операции.

## <a name="syntax"></a>Синтаксис

```cpp
inline void CurrentStatus(
   Details::AsyncStatusInternal *status
);
```

### <a name="parameters"></a>Параметры

*status*<br/>
Расположение, в котором эта операция сохраняет текущее состояние.

## <a name="remarks"></a>Примечания

Данная операция является потокобезопасной.

## <a name="requirements"></a>Требования

**Заголовок:** async.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс AsyncBase](../windows/asyncbase-class.md)<br/>
[Перечисление AsyncStatusInternal](../windows/asyncstatusinternal-enumeration.md)