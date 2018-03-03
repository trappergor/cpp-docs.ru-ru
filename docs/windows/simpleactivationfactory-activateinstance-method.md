---
title: "Метод SimpleActivationFactory::ActivateInstance | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory::ActivateInstance
dev_langs:
- C++
helpviewer_keywords:
- ActivateInstance method
ms.assetid: 4f836e51-5a6c-4bad-b871-9f25199298b4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6bbe9d8c215674f087c6e0fa4ca7f3439fb89b78
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="simpleactivationfactoryactivateinstance-method"></a>Метод SimpleActivationFactory::ActivateInstance

Создает экземпляр указанного интерфейса.

## <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD( ActivateInstance )(
    _Deref_out_ IInspectable **ppvObject
);
```

### <a name="parameters"></a>Параметры

*ppvObject*  
После завершения операции, указатель на экземпляр объекта, заданного параметром `Base` параметре шаблона класса.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="remarks"></a>Примечания

Если &#95; &#95; WRL_STRICT &#95; &#95; будет определено, Ошибка утверждения создается, если базовый класс, указанный в параметре шаблона класса не является производным от [RuntimeClass](../windows/runtimeclass-class.md), или не настроен со значением WinRt или WinRtClassicComMix [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) значение перечисления.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс SimpleActivationFactory](../windows/simpleactivationfactory-class.md)