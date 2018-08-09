---
title: Метод SimpleActivationFactory::ActivateInstance | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory::ActivateInstance
dev_langs:
- C++
helpviewer_keywords:
- ActivateInstance method
ms.assetid: 4f836e51-5a6c-4bad-b871-9f25199298b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 260d7e2993bd92297167c23458d37ba80919306f
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40013389"
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

Если `__WRL_STRICT__` будет определен, Ошибка утверждения создается, если базовый класс, указанный в параметре шаблона класса не является производным от [RuntimeClass](../windows/runtimeclass-class.md), или не настроен со значением WinRt или WinRtClassicComMix [ RuntimeClassType](../windows/runtimeclasstype-enumeration.md) значение перечисления.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также
 [Класс SimpleActivationFactory](../windows/simpleactivationfactory-class.md)