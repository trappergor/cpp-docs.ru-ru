---
title: Метод AsyncBase::ContinueAsyncOperation | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::ContinueAsyncOperation
dev_langs:
- C++
helpviewer_keywords:
- ContinueAsyncOperation method
ms.assetid: ce38181d-2fc3-4579-b0ce-237a3c7648bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b83d7a0bb5eadede42d2572d5ebc5a02a0fe9a0e
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42607189"
---
# <a name="asyncbasecontinueasyncoperation-method"></a>Метод AsyncBase::ContinueAsyncOperation

Определяет, должны продолжать обработку асинхронной операции или следует остановить.

## <a name="syntax"></a>Синтаксис

```cpp
inline bool ContinueAsyncOperation();
```

## <a name="return-value"></a>Возвращаемое значение

**значение true,** Если текущее состояние асинхронной операции *работы*, который означает, что операция должна продолжаться. В противном случае **false**, который означает, что операция следует остановить.

## <a name="requirements"></a>Требования

**Заголовок:** async.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс AsyncBase](../windows/asyncbase-class.md)