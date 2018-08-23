---
title: Метод AsyncBase::TryTransitionToCompleted | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::TryTransitionToCompleted
dev_langs:
- C++
helpviewer_keywords:
- TryTransitionToCompleted method
ms.assetid: 8d038e0a-47ec-4cfc-8aeb-6821282df67a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3f1f6e27c7797a8995044bdcf9ebd9425a6f6ea3
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42604167"
---
# <a name="asyncbasetrytransitiontocompleted-method"></a>Метод AsyncBase::TryTransitionToCompleted

Указывает, завершена ли текущей асинхронной операции.

## <a name="syntax"></a>Синтаксис

```cpp
bool TryTransitionToCompleted(
   void
);
```

## <a name="return-value"></a>Возвращаемое значение

**значение true,** Если асинхронная операция была завершена; в противном случае **false**.

## <a name="requirements"></a>Требования

**Заголовок:** async.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс AsyncBase](../windows/asyncbase-class.md)