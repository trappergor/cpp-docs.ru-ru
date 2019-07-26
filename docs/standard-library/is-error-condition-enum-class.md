---
title: Класс is_error_condition_enum
ms.date: 11/04/2016
f1_keywords:
- system_error/std::is_error_condition_enum
helpviewer_keywords:
- is_error_condition_enum class
ms.assetid: 752bb87a-c61c-4304-9254-5aaf228b59c0
ms.openlocfilehash: c40f8f6eb93a33098cfbcf8133f08c56285abb43
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452606"
---
# <a name="iserrorconditionenum-class"></a>Класс is_error_condition_enum

Представляет тип предиката, проверяющий перечисление [error_condition](../standard-library/error-condition-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
template <_Enum>
    class is_error_condition_enum;
```

## <a name="remarks"></a>Примечания

Экземпляр этого [предиката типа](../standard-library/type-traits.md) содержит значение true, если тип `_Enum` является значением перечисления, подходящим для хранения в объекте типа `error_condition`.

Допускается добавление специализации в этот тип для определяемых пользователем типов.

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)
