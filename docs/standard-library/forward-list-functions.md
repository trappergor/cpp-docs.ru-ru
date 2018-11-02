---
title: Функции &lt;forward_list&gt;
ms.date: 11/04/2016
f1_keywords:
- forward_list/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
ms.openlocfilehash: b425461f1428470b04a525efdd9a702ae038a283
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477341"
---
# <a name="ltforwardlistgt-functions"></a>Функции &lt;forward_list&gt;

||
|-|
|[swap](#swap)|

## <a name="swap"></a>  swap

Меняет местами элементы двух прямых списков.

```cpp
void swap(
    forward_list <Type, Allocator>& left,
    forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*left*|Объект типа `forward_list`.|
|*right*|Объект типа `forward_list`.|

### <a name="remarks"></a>Примечания

Шаблонная функция выполняет `left.swap(right)`.

## <a name="see-also"></a>См. также

[<forward_list>](../standard-library/forward-list.md)<br/>
