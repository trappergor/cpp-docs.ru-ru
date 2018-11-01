---
title: ActivationFactoryCallback - функция
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::ActivationFactoryCallback
helpviewer_keywords:
- ActivationFactoryCallback function
ms.assetid: dd40c79b-1273-4f2a-8c24-ae9926fb4fd9
ms.openlocfilehash: 8da0f3f54e142673a44909f3fe2141b09a71d388
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50586450"
---
# <a name="activationfactorycallback-function"></a>ActivationFactoryCallback - функция

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
inline HRESULT STDAPICALLTYPE ActivationFactoryCallback(
   HSTRING activationId,
   IActivationFactory **ppFactory
);
```

### <a name="parameters"></a>Параметры

*activationId*<br/>
Дескриптор строка, задающая имя класса среды выполнения.

*ppFactory*<br/>
После завершения операции фабрику активации, соответствующее параметру *activationId*.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя. Скорее всего, ошибочные значения HRESULT: CLASS_E_CLASSNOTAVAILABLE и E_INVALIDARG.

## <a name="remarks"></a>Примечания

Возвращает фабрику активации для активации указанного идентификатора.

Среда выполнения Windows вызывает эту функцию обратного вызова для запроса объекта, заданный его именем класса среды выполнения.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)