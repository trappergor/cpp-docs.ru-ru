---
title: Класс is_error_code_enum | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- system_error/std::is_error_code_enum
dev_langs:
- C++
helpviewer_keywords:
- is_error_code_enum class
ms.assetid: cee5be2d-7c20-4cec-a352-1ab8b7d32601
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d7024817c5a02d7c4a529167ca65a292b34be119
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33844605"
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
