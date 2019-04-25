---
title: Класс is_error_condition_enum
ms.date: 11/04/2016
f1_keywords:
- system_error/std::is_error_condition_enum
helpviewer_keywords:
- is_error_condition_enum class
ms.assetid: 752bb87a-c61c-4304-9254-5aaf228b59c0
ms.openlocfilehash: 1b5b55431db806bb109a58199ad9d2d7c16f38ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62162438"
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

## <a name="requirements"></a>Требования

**Заголовок:** \<system_error>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[<system_error>](../standard-library/system-error.md)<br/>
