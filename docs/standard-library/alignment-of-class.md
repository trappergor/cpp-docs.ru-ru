---
title: Класс alignment_of
ms.date: 12/11/2019
f1_keywords:
- type_traits/std::alignment_of
helpviewer_keywords:
- alignment_of class
- alignment_of
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
ms.openlocfilehash: d241848edf57fe4876c35e22f1762abf5d6888fa
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302319"
---
# <a name="alignment_of-class"></a>Класс alignment_of

Получает выравнивание указанного типа. Эта структура реализована на основе [alignof](../cpp/alignment-cpp-declarations.md). Используйте **alignof** напрямую, когда нужно просто запросить значение выравнивания. Используйте функцию alignment_of, когда нужна целочисленная константа, например, при отправке тегов.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct alignment_of;
```

### <a name="parameters"></a>Параметры

*Ty*\
Запрашиваемый тип.

## <a name="remarks"></a>Заметки

Запрос типа содержит значение выравнивания типа *Ty*.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits >

**Пространство имен:** std

## <a name="see-also"></a>См. также:

[<type_traits>](../standard-library/type-traits.md)\
[Класс aligned_storage](../standard-library/aligned-storage-class.md)
