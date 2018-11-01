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
ms.openlocfilehash: 65648d62657bf989d4a08660e0fd7724511350c1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666301"
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

[Пространство имен Windows::Foundation](../windows/windows-foundation-namespace.md)