---
title: Activateinstance-функция | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Windows::Foundation::ActivateInstance
- client/ABI::Windows::Foundation::ActivateInstance
dev_langs:
- C++
helpviewer_keywords:
- ActivateInstance function
ms.assetid: 8cfd1dd9-5fda-4cc2-acf8-d40e783b3875
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ebebe0bbceafe82c41ec99b2532c965670776127
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426397"
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