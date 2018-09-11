---
title: Метод AsyncBase::Close | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: a52b1124-754b-4393-b491-64aae0c22f1c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 732eb6f8668f7742e23e1ea410dcc659bc3d36c7
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605350"
---
# <a name="asyncbaseclose-method"></a>Метод AsyncBase::Close

Закрывает асинхронной операции.

## <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(
   Close
)(void) override;
```

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция закрывает или уже закрыт; в противном случае E_ILLEGAL_STATE_CHANGE.

## <a name="remarks"></a>Примечания

**Метод Close()** — это реализация по умолчанию `IAsyncInfo::Close`, а не фактические работает. Чтобы действительно закрыть асинхронную операцию, переопределите `OnClose()` чисто виртуального метода.

## <a name="requirements"></a>Требования

**Заголовок:** async.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс AsyncBase](../windows/asyncbase-class.md)