---
title: '&lt;списка функций&gt; | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- list/std::swap
ms.openlocfilehash: 04f00a9274018432cd03917ae5485f2d395649e4
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78874445"
---
# <a name="ltlistgt-functions"></a>&lt;списка функций&gt;

## <a name="swap"></a>позиции

Меняет местами элементы двух списков.

```cpp
template <class T, class Allocator>
    void swap(list<T, Allocator>& left, list<T, Allocator>& right)
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `list`.

*справа*\
Объект типа `list`.

### <a name="remarks"></a>Remarks

Шаблонная функция выполняет `left.swap(right)`.
