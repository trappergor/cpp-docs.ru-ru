---
title: GetActivationFactory - функция
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::GetActivationFactory
- client/ABI::Windows::Foundation::GetActivationFactory
- client/Windows::Foundation::GetActivationFactory
helpviewer_keywords:
- GetActivationFactory function
ms.assetid: 5736d285-6beb-42aa-8788-e261c0010afe
ms.openlocfilehash: a2581fce3c15c96317bf68de0ed918b19edd8b38
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481716"
---
# <a name="getactivationfactory-function"></a>GetActivationFactory - функция

Извлекает фабрику активации для типа, указанного в параметре шаблона.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename T>
inline HRESULT GetActivationFactory(
   _In_ HSTRING activatableClassId,
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> factory
);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Параметр шаблона, который определяет тип фабрики активации.

*activatableClassId*<br/>
Имя класса, который может создать фабрика активации.

*фабрики*<br/>
После завершения операции, ссылка на фабрику активации для типа *T*.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее причину неудачного завершения операции.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Windows::Foundation

## <a name="see-also"></a>См. также

[Пространство имен Windows::Foundation](../windows/windows-foundation-namespace.md)