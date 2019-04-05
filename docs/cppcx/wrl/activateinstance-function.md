---
title: ActivateInstance - функция
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Windows::Foundation::ActivateInstance
- client/ABI::Windows::Foundation::ActivateInstance
helpviewer_keywords:
- ActivateInstance function
ms.assetid: 8cfd1dd9-5fda-4cc2-acf8-d40e783b3875
ms.openlocfilehash: 43aa34153f0e71dd665090243ff2288bff704404
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59029084"
---
# <a name="activateinstance-function"></a>ActivateInstance - функция

Регистрирует и возвращает экземпляр заданного типа, определенного в идентификатор указанного класса.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename T>
inline HRESULT ActivateInstance(
   _In_ HSTRING activatableClassId,
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> instance
);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Типа, подлежащего активации.

*activatableClassId*<br/>
Имя идентификатора класса, определяет параметр *T*.

*экземпляр*<br/>
После завершения операции, ссылку на экземпляр *T*.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае ошибку HRESULT, которые указывают на причину ошибки.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Windows::Foundation

## <a name="see-also"></a>См. также

[Пространство имен Windows::Foundation](windows-foundation-namespace.md)