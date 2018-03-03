---
title: "Метод RuntimeClass::GetTrustLevel | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::GetTrustLevel
dev_langs:
- C++
helpviewer_keywords:
- GetTrustLevel method
ms.assetid: bd90407e-6dd7-41c3-9ea0-c402c276014a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 89a00c052ec1191cd57057f52401954397169b88
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="runtimeclassgettrustlevel-method"></a>Метод RuntimeClass::GetTrustLevel

Возвращает текущий объект RuntimeClass уровень доверия.

## <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(GetTrustLevel)(
    _Out_ TrustLevel* trustLvl
);
```

### <a name="parameters"></a>Параметры

*trustLvl*  
После завершения операции уровня доверия для текущего объекта RuntimeClass.

## <a name="return-value"></a>Возвращаемое значение

Всегда возвращает значение S_OK.

## <a name="remarks"></a>Примечания

Ошибка assert, если порожденный &#95; &#95; WRL_STRICT &#95; &#95; или &#95; &#95; WRL_FORCE_INSPECTABLE_CLASS_MACRO &#95; &#95; не определен.

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс RuntimeClass](../windows/runtimeclass-class.md)