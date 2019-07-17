---
title: '&lt;список&gt; функции | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- list/std::swap
ms.openlocfilehash: 04f00a9274018432cd03917ae5485f2d395649e4
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68269026"
---
# <a name="ltlistgt-functions"></a>&lt;список&gt; функции

## <a name="swap"></a> Swap

Меняет местами элементы двух списков.

```cpp
template <class T, class Allocator>
    void swap(list<T, Allocator>& left, list<T, Allocator>& right)
```

### <a name="parameters"></a>Параметры

*Слева*\
Объект типа `list`.

*Правильно*\
Объект типа `list`.

### <a name="remarks"></a>Примечания

Шаблонная функция выполняет `left.swap(right)`.
