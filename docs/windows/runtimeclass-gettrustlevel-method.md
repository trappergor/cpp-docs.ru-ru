---
title: Метод RuntimeClass::GetTrustLevel | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::GetTrustLevel
dev_langs:
- C++
helpviewer_keywords:
- GetTrustLevel method
ms.assetid: bd90407e-6dd7-41c3-9ea0-c402c276014a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 98bd73d2c067e6d5bbb4425782de594bbaa47bc1
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606628"
---
# <a name="runtimeclassgettrustlevel-method"></a>Метод RuntimeClass::GetTrustLevel

Получает уровень доверия текущего **RuntimeClass** объекта.

## <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(GetTrustLevel)(
    _Out_ TrustLevel* trustLvl
);
```

### <a name="parameters"></a>Параметры

*trustLvl*  
После завершения операции, уровень доверия текущего **RuntimeClass** объекта.

## <a name="return-value"></a>Возвращаемое значение

Всегда значение S_OK.

## <a name="remarks"></a>Примечания

Ошибка assert создается в том случае, если &#95; &#95;WRL_STRICT&#95; &#95; или &#95; &#95;WRL_FORCE_INSPECTABLE_CLASS_MACRO&#95; &#95; не определена.

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также
 [Класс RuntimeClass](../windows/runtimeclass-class.md)