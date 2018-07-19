---
title: Метод RuntimeClass::GetTrustLevel | Документы Microsoft
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
ms.openlocfilehash: bc588950cc8752a7c2b8e1ddf00b2193aaf0f395
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892635"
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

Если выдается ошибка утверждения &#95; &#95;WRL_STRICT&#95; &#95; или &#95; &#95;WRL_FORCE_INSPECTABLE_CLASS_MACRO&#95; &#95; не определена.

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс RuntimeClass](../windows/runtimeclass-class.md)