---
title: Класс alignment_of | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::alignment_of
dev_langs:
- C++
helpviewer_keywords:
- alignment_of class
- alignment_of
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9af19f046cf6de44448e3fcddf97584f58adc9ae
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="alignmentof-class"></a>Класс alignment_of

Получает выравнивание указанного типа. Эта структура реализована на основе [alignof](../cpp/alignof-and-alignas-cpp.md). Используйте `alignof` напрямую, если нужно просто запросить значение выравнивания. Используйте функцию alignment_of, когда нужна целочисленная константа, например, при отправке тегов.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct alignment_of;
```

### <a name="parameters"></a>Параметры

`Ty` Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Запрос типа содержит значение выравнивания типа `Ty`.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс aligned_storage](../standard-library/aligned-storage-class.md)<br/>
