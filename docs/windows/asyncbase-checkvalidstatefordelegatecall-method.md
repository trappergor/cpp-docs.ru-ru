---
title: Метод AsyncBase::CheckValidStateForDelegateCall | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::CheckValidStateForDelegateCall
dev_langs:
- C++
helpviewer_keywords:
- CheckValidStateForDelegateCall method
ms.assetid: d997ebe7-2378-4e74-a379-f0f85e6922f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cd3629fcaf8507abd2baf6cded3c6a63bc6fd64f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611504"
---
# <a name="asyncbasecheckvalidstatefordelegatecall-method"></a>Метод AsyncBase::CheckValidStateForDelegateCall

Проверяет, является ли делегат свойства можно изменить в текущем состоянии асинхронной.

## <a name="syntax"></a>Синтаксис

```cpp
inline HRESULT CheckValidStateForDelegateCall();
```

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если делегат свойства можно изменить; в противном случае E_ILLEGAL_METHOD_CALL.

## <a name="requirements"></a>Требования

**Заголовок:** async.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс AsyncBase](../windows/asyncbase-class.md)