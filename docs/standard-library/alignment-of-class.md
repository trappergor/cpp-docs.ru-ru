---
title: Класс alignment_of | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::alignment_of
dev_langs:
- C++
helpviewer_keywords:
- alignment_of class
- alignment_of
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0089d190b28489d2274df2209890bc3a391b6f66
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44103857"
---
# <a name="alignmentof-class"></a>Класс alignment_of

Получает выравнивание указанного типа. Эта структура реализована на основе [alignof](../cpp/alignof-and-alignas-cpp.md). Используйте `alignof` напрямую, если нужно просто запросить значение выравнивания. Используйте функцию alignment_of, когда нужна целочисленная константа, например, при отправке тегов.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct alignment_of;
```

### <a name="parameters"></a>Параметры

*Ty*<br/>
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Запрос типа содержит значение выравнивания типа *Ty*.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс aligned_storage](../standard-library/aligned-storage-class.md)<br/>
