---
title: Класс is_error_code_enum
ms.date: 11/04/2016
f1_keywords:
- system_error/std::is_error_code_enum
helpviewer_keywords:
- is_error_code_enum class
ms.assetid: cee5be2d-7c20-4cec-a352-1ab8b7d32601
ms.openlocfilehash: d890eb6a1b7c93f9ae5b87018c3bf1d6eeae8abb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62336484"
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

## <a name="requirements"></a>Требования

**Заголовок:** \<system_error>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[<system_error>](../standard-library/system-error.md)<br/>
