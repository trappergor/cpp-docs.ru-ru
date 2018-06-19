---
title: Метод SimpleActivationFactory::GetRuntimeClassName | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName
dev_langs:
- C++
ms.assetid: 3aa07487-9a42-46f8-8893-37ba6315e50b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e001d0269c21026bdd00abcdd4d257f11d601cf6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889037"
---
# <a name="simpleactivationfactorygetruntimeclassname-method"></a>Метод SimpleActivationFactory::GetRuntimeClassName

Получает имя класса среды выполнения экземпляра класса, указанного в параметре шаблона класса `Base`.

## <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

### <a name="parameters"></a>Параметры

*runtimeName*  
После завершения операции представляет имя класса среды выполнения.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="remarks"></a>Примечания

Если &#95; &#95;WRL_STRICT&#95; &#95; будет определено, Ошибка утверждения создается, если класс, указанный `Base` параметре шаблона класса не является производным от [RuntimeClass](../windows/runtimeclass-class.md), или не настроен со WinRt или WinRtClassicComMix [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) значение перечисления.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс SimpleActivationFactory](../windows/simpleactivationfactory-class.md)