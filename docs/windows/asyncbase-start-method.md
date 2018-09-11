---
title: Метод AsyncBase::Start | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::Start
dev_langs:
- C++
helpviewer_keywords:
- Start method
ms.assetid: 67405c9d-0d1a-4c1e-8ea4-6ba01c1f90d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d81a3f29e99f49b03eb76f44af60c42d433e0bdc
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611236"
---
# <a name="asyncbasestart-method"></a>Метод AsyncBase::Start

Начинает асинхронную операцию.

## <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(
   Start
)(void);
```

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция запускается или уже запущен; в противном случае E_ILLEGAL_STATE_CHANGE.

## <a name="remarks"></a>Примечания

**Start()** — это реализация по умолчанию `IAsyncInfo::Start`, а не фактические работает. Чтобы фактически запускает асинхронную операцию, переопределите `OnStart()` чисто виртуального метода.

## <a name="requirements"></a>Требования

**Заголовок:** async.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс AsyncBase](../windows/asyncbase-class.md)