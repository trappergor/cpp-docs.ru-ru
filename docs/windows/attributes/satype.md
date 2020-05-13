---
title: сатипе (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.satype
helpviewer_keywords:
- satype attribute
ms.assetid: 1716590b-6bcb-4aba-b1bc-82f7335f02c3
ms.openlocfilehash: 4619deec6d5e4e9083fbc7bcab53caee0101285c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166280"
---
# <a name="satype"></a>satype

Указывает тип данных структуры `SAFEARRAY`.

## <a name="syntax"></a>Синтаксис

```cpp
[ satype(data_type) ]
```

### <a name="parameters"></a>Параметры

*data_type*<br/>
Тип данных `SAFEARRAY` структуры данных, передаваемой в качестве параметра методу интерфейса.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Параметр интерфейса, метод интерфейса|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

## <a name="remarks"></a>Remarks

Атрибут **сатипе** C++ задает тип данных `SAFEARRAY`.

> [!NOTE]
> Уровень косвенного обращения удаляется из указателя `SAFEARRAY` в созданном IDL-файле из того, как он объявлен в cpp-файле.

## <a name="example"></a>Пример

```cpp
// cpp_attr_ref_satype.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyModule")];
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface A {
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);
};
```

## <a name="see-also"></a>См. также раздел

[Атрибуты компилятора](compiler-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[идентификатор](id.md)
