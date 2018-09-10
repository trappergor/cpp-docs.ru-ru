---
title: Функция to_vector | Документация Майкрософт
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
f1_keywords:
- collection/Windows::Foundation::Collections::to_vector
dev_langs:
- C++
helpviewer_keywords:
- to_vector Function
ms.assetid: 9cdd5123-7243-4def-a1d3-162e0bf6219e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3dcccc332a5d768a614414838003e1400f3c6a6
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107631"
---
# <a name="tovector-function"></a>Функция to_vector

Возвращает объект `std::vector` , значение которого совпадает с коллекцией, лежащей в основе указанного параметра IVector или IVectorView.

## <a name="syntax"></a>Синтаксис

```
template <typename T>
inline ::std::vector<T> to_vector(IVector<T>^ v);

template <typename T>
inline ::std::vector<T> to_vector(IVectorView<T>^ v);
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Параметр типа шаблона.

*v*<br/>
Интерфейс IVector или IVectorView, который предоставляет доступ к базовому объекту Vector или VectorView.

### <a name="return-value"></a>Возвращаемое значение

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Windows::Foundation::Collections

## <a name="see-also"></a>См. также

[Пространство имен Windows::Foundation:: Collections](../cppcx/windows-foundation-collections-namespace-c-cx.md)