---
title: Оператор operator== (Microsoft::WRL)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::operator==
ms.assetid: 94f383a5-17a9-40c7-9d9c-778acdc54b27
ms.openlocfilehash: 4774d4801f917691610a457105fc6690ab030a44
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226910"
---
# <a name="operator-operator-microsoftwrl"></a>Оператор operator== (Microsoft::WRL)

Оператор равенства для объектов [ComPtr](comptr-class.md) и [ComPtrRef](comptrref-class.md) .

## <a name="syntax"></a>Синтаксис

```cpp
WRL_NOTHROW bool operator==(
   const ComPtr<T>& a,
   const ComPtr<U>& b
);
WRL_NOTHROW bool operator==(
   const ComPtr<T>& a,
   decltype(__nullptr)
);
WRL_NOTHROW bool operator==(
   decltype(__nullptr),
   const ComPtr<T>& a
);
WRL_NOTHROW bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   const Details::ComPtrRef<ComPtr<U>>& b
);
WRL_NOTHROW bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   decltype(__nullptr)
);
WRL_NOTHROW bool operator==(
   decltype(__nullptr),
   const Details::ComPtrRef<ComPtr<T>>& a
);
WRL_NOTHROW bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   void* b
);
WRL_NOTHROW bool operator==(
   void* b,
   const Details::ComPtrRef<ComPtr<T>>& a
);
```

### <a name="parameters"></a>Параметры

*конкретного*<br/>
Левый объект.

*&*<br/>
Правый объект.

## <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если объекты равны; в противном случае — **`false`** .

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также статью

[Пространство имен Microsoft:: WRL](microsoft-wrl-namespace.md)
