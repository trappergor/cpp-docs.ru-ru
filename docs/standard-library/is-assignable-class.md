---
title: Класс is_assignable | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_assignable
ms.assetid: 53444287-c8be-4ad2-9487-a85c066a4f84
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9e8ee756ce98e1476f10c04c10da1c6bce486513
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="isassignable-class"></a>Класс is_assignable

Проверяет, можно ли назначить значение типа `From` типу `To`.

## <a name="syntax"></a>Синтаксис

```cpp
template <class To, class From>
struct is_assignable;
```

### <a name="parameters"></a>Параметры

Тип объекта, который получает назначение.

От типа объекта, который предоставляет значение.

## <a name="remarks"></a>Примечания

Невычисленное выражение `declval<To>() = declval<From>()` должно иметь правильный формат. `From` и `To` должны быть полными типами, `void` или массивами с неизвестной границей.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
