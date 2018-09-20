---
title: Метод AsyncBase::TryTransitionToError | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::TryTransitionToError
dev_langs:
- C++
helpviewer_keywords:
- TryTransitionToError method
ms.assetid: f6d11c25-1ce3-43f9-af1c-97c4dc0f6f0f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a6e21f89b5f1beb035b2dd87b2d0ad1d55bc3f8f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418064"
---
# <a name="asyncbasetrytransitiontoerror-method"></a>Метод AsyncBase::TryTransitionToError

Указывает, является ли указанный код ошибки можно изменить внутреннее состояние ошибки.

## <a name="syntax"></a>Синтаксис

```cpp
bool TryTransitionToError(
   const HRESULT error
);
```

### <a name="parameters"></a>Параметры

*Ошибка*<br/>
Ошибка HRESULT.

## <a name="return-value"></a>Возвращаемое значение

**значение true,** если внутреннее состояние ошибки было изменено; в противном случае — значение **false**.

## <a name="remarks"></a>Примечания

Эта операция изменяет состояние ошибки только в том случае, если состояние ошибки уже имеет значение S_OK. Эта операция не оказывает влияния Если состояние ошибки не ошибка, отменено, завершено или закрыт.

## <a name="requirements"></a>Требования

**Заголовок:** async.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс AsyncBase](../windows/asyncbase-class.md)