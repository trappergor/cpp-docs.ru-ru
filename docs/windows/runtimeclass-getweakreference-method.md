---
title: Метод RuntimeClass::GetWeakReference | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::GetWeakReference
dev_langs:
- C++
helpviewer_keywords:
- GetWeakReference method
ms.assetid: 26656ace-7f20-4364-87c9-4a75dd30912e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cc4d2e542afcd72426cb3b0aba57b7d7cbabad06
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42583648"
---
# <a name="runtimeclassgetweakreference-method"></a>Метод RuntimeClass::GetWeakReference

Получает указатель на объект слабой ссылки для текущего **RuntimeClass** объекта.

## <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(
   GetWeakReference
)(_Deref_out_ IWeakReference **weakReference);
```

### <a name="parameters"></a>Параметры

*weakReference*  
После завершения операции представляет указатель на объект слабой ссылки.

## <a name="return-value"></a>Возвращаемое значение

Всегда значение S_OK.

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс RuntimeClass](../windows/runtimeclass-class.md)