---
title: Класс is_destructible | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_destructible
dev_langs:
- C++
helpviewer_keywords:
- is_destructible
ms.assetid: 3bb9b718-1ad5-49ae-93cc-92b93b546b4d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41a5da108c082dc4199a216d36f51d41e1748ada
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33844293"
---
# <a name="isdestructible-class"></a>Класс is_destructible

Проверяет, можно ли уничтожить тип.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct is_destructible;
```

### <a name="parameters"></a>Параметры

`T` Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа имеет значение true, если тип `T` можно уничтожить, в противном случае — значение false. К типам, которые можно уничтожить, относятся ссылочные типы, типы объектов и типы, для которых при типе `U` , равном `remove_all_extents_t<T>` , невычисленный операнд `std::declval<U&>.~U()` имеет правильный формат. Другие типы, включая незавершенные, `void`и типы функций, не являются типами, которые можно уничтожить.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
