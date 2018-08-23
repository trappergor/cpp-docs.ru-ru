---
title: Метод ComPtr::AsWeak | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::AsWeak
dev_langs:
- C++
helpviewer_keywords:
- AsWeak method
ms.assetid: 23e29dcd-39cb-423f-abe6-6df4428213bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d8de0ee1bf4d879490002d3483f0340714b989ac
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42581228"
---
# <a name="comptrasweak-method"></a>Метод ComPtr::AsWeak

Извлекает слабую ссылку на текущий объект.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT AsWeak(
   _Out_ WeakRef* pWeakRef
);
```

### <a name="parameters"></a>Параметры

*pWeakRef*  
После завершения операции представляет указатель на объект слабой ссылки.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс ComPtr](../windows/comptr-class.md)