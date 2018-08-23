---
title: Метод AsyncBase::ErrorCode | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::ErrorCode
dev_langs:
- C++
helpviewer_keywords:
- ErrorCode method
ms.assetid: 3f5f0f69-d60a-4a67-8cc6-a55fdc89a192
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7336824d04745440a1f6152ebacfed2afc62258e
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602382"
---
# <a name="asyncbaseerrorcode-method"></a>Метод AsyncBase::ErrorCode

Получает код ошибки для текущей асинхронной операции.

## <a name="syntax"></a>Синтаксис

```cpp
inline void ErrorCode(
   HRESULT *error
);
```

### <a name="parameters"></a>Параметры

*Ошибка*  
Расположение, в котором эта операция сохраняет текущий код ошибки.

## <a name="remarks"></a>Примечания

Данная операция является потокобезопасной.

## <a name="requirements"></a>Требования

**Заголовок:** async.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс AsyncBase](../windows/asyncbase-class.md)