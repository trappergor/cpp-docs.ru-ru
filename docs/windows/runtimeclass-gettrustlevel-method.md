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
ms.openlocfilehash: c714f37a53e111c90333352610fd73532ac86fe7
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599836"
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

Ошибка assert создается в том случае, если `__WRL_STRICT__` или `__WRL_FORCE_INSPECTABLE_CLASS_MACRO__` не определена.

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс RuntimeClass](../windows/runtimeclass-class.md)