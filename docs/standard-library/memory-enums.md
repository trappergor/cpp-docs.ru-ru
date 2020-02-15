---
title: Перечисления &lt;memory&gt;
ms.date: 11/04/2016
f1_keywords:
- memory/std::pointer_safety
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
ms.openlocfilehash: 78cdb0fe6c0d9487500804d21fe4ad4870fcad0f
ms.sourcegitcommit: 8414cd91297dea88c480e208c7b5301db9972f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77257836"
---
# <a name="ltmemorygt-enums"></a>Перечисления &lt;memory&gt;

## <a name="pointer_safety"></a>Перечисление pointer_safety

Перечисление возможных значений, возвращаемых `get_pointer_safety`.

```cpp
class pointer_safety {
   relaxed,
   preferred,
   strict
};
```

### <a name="remarks"></a>Примечания

**Перечисление** с заданной областью определяет значения, которые могут быть возвращены `get_pointer_safety()`.

`relaxed` — указатели, наследованные небезопасно (указатели на объявленные объекты или объекты, для которых выделена память), обрабатываются так же, как наследованные безопасно.

`preferred` — как и раньше, но указатели, наследованные небезопасно, не должны разыменовываться.

`strict` — указатели, наследованные небезопасно, могут обрабатываться не так, как наследованные безопасно.
