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
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303978"
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