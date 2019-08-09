---
title: Класс is_error_code_enum
ms.date: 11/04/2016
f1_keywords:
- system_error/std::is_error_code_enum
helpviewer_keywords:
- is_error_code_enum class
ms.assetid: cee5be2d-7c20-4cec-a352-1ab8b7d32601
ms.openlocfilehash: 4080c62034b224a9553eca2787aa1c2f2cf69ab8
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454635"
---
# <a name="iserrorcodeenum-class"></a>Класс is_error_code_enum

Представляет тип предиката, проверяющий перечисление [error_code](../standard-library/error-code-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
template <_Enum>
    class is_error_code_enum;
```

## <a name="remarks"></a>Примечания

Экземпляр этого [предиката типа](../standard-library/type-traits.md) содержит значение true, если тип `_Enum` является значением перечисления, подходящим для хранения в объекте типа `error_code`.

Допускается добавление специализации в этот тип для определяемых пользователем типов.

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)
