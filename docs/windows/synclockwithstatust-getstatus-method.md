---
title: Метод SyncLockWithStatusT::GetStatus | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus
dev_langs:
- C++
helpviewer_keywords:
- GetStatus method
ms.assetid: d448b51d-a63d-40d9-a9ee-4aad3204118d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c2cef491aac3350c1692c2f87236f3cbf01dd9b0
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42612082"
---
# <a name="synclockwithstatustgetstatus-method"></a>Метод SyncLockWithStatusT::GetStatus

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
DWORD GetStatus() const;
```

## <a name="return-value"></a>Возвращаемое значение

Результат операции ожидания на объект, который основан на **SyncLockWithStatusT** класс, например [мьютекс](../windows/mutex-class1.md) или [семафора](../windows/semaphore-class.md). Ноль (0) указывает, что операция ожидания возвращается в сигнальном состоянии; в противном случае — другой возникло состояние, такие как прошедшее значение времени ожидания.

## <a name="remarks"></a>Примечания

Получает сведения о состоянии ожидания текущего **SyncLockWithStatusT** объекта.

Функция GetStatus() извлекает значение базового [status_](../windows/synclockwithstatust-status-data-member.md) данные-член. Если создан на основе объекта **SyncLockWithStatusT** класс выполняет операцию блокировки, объект сначала ожидает объект станет доступным. Результат этой операции ожидания сохраняется в `status_` элемент данных. Возможные значения `status_` элемент данных являются возвращаемыми значениями для операции ожидания. Дополнительные сведения см. в разделе возвращаемые значения `WaitForSingleObjectEx()` функция в библиотеке MSDN.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>См. также

[Класс SyncLockWithStatusT](../windows/synclockwithstatust-class.md)