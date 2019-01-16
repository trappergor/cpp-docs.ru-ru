---
title: Константы математических ошибок
ms.date: 11/04/2016
f1_keywords:
- _PLOSS
- _UNDERFLOW
- _TLOSS
- _SING
- _DOMAIN
- _OVERFLOW
helpviewer_keywords:
- _TLOSS constant
- _SING constant
- PLOSS constant
- UNDERFLOW constant
- _UNDERFLOW constant
- _OVERFLOW constant
- DOMAIN constant
- OVERFLOW constant
- TLOSS constant
- SING constant
- _DOMAIN constant
- _PLOSS constant
- math error constants
ms.assetid: 4be933a6-674e-45a5-8ac9-090023542f5b
ms.openlocfilehash: b159d5dbe434f4ce63b7b93f60aca89b51437812
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220027"
---
# <a name="math-error-constants"></a>Константы математических ошибок

## <a name="syntax"></a>Синтаксис

```
#include <math.h>
```

## <a name="remarks"></a>Примечания

Математические подпрограммы библиотеки времени выполнения могут генерировать константы математических ошибок.

Эти ошибки, описанные ниже, соответствуют типам исключений, определенным в файле MATH.H, и возвращаются функцией `_matherr`, когда возникает математическая ошибка.

|Константа|Значение|
|--------------|-------------|
|`_DOMAIN`|Значение аргумента функции находится вне домена функции.|
|`_OVERFLOW`|Результат слишком велик для представления в виде типа возвращаемого значения функции.|
|`_PLOSS`|Произошла частичная потеря значимости.|
|`_SING`|Сингулярность аргумента: аргумент функции имеет недопустимое значение. (Например, значение 0 передается в функцию, для которой требуется ненулевое значение.)|
|`_TLOSS`|Произошла полная потеря значимости.|
|`_UNDERFLOW`|Результат слишком мал для представления.|

## <a name="see-also"></a>См. также раздел

[_matherr](../c-runtime-library/reference/matherr.md)<br/>
[Глобальные константы](../c-runtime-library/global-constants.md)
