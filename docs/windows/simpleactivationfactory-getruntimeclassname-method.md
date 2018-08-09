---
title: Метод SimpleActivationFactory::GetRuntimeClassName | Документация Майкрософт
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
ms.openlocfilehash: 9c8bc1962e946a48b6ebebaf072e4cb32559a6de
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014712"
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

Если `__WRL_STRICT__` будет определен, Ошибка утверждения создается, если класс, указанный `Base` параметре шаблона класса не является производным от [RuntimeClass](../windows/runtimeclass-class.md), или не настроен со значением WinRt или WinRtClassicComMix [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) значение перечисления.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также
 [Класс SimpleActivationFactory](../windows/simpleactivationfactory-class.md)