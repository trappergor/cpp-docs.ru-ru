---
title: Перечисления &lt;memory&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- memory/std::pointer_safety
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
ms.openlocfilehash: 9b9ea485bb66292c3c0509036c22dd161a694dd3
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38961426"
---
# <a name="ltmemorygt-enums"></a>Перечисления &lt;memory&gt;

||
|-|
|[pointer_safety](#pointer_safety)|

## <a name="pointer_safety"></a>  Перечисление pointer_safety

Перечисление возможных значений, возвращаемых `get_pointer_safety`.

class pointer_safety { relaxed, preferred, strict };

### <a name="remarks"></a>Примечания

Ограниченную **перечисления** определяет значения, которые могут быть возвращены `get_pointer_safety()`:

`relaxed` — указатели, наследованные небезопасно (указатели на объявленные объекты или объекты, для которых выделена память), обрабатываются так же, как наследованные безопасно.

`preferred` — как и раньше, но указатели, наследованные небезопасно, не должны разыменовываться.

`strict` — указатели, наследованные небезопасно, могут обрабатываться не так, как наследованные безопасно.

## <a name="see-also"></a>См. также

[\<memory>](../standard-library/memory.md)<br/>
