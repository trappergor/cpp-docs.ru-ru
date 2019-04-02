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
ms.openlocfilehash: 82c83e95648eeb0fc8985777156659a2ffb876a8
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58784753"
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

[Пространство имен Windows::Foundation](windows-foundation-namespace.md)