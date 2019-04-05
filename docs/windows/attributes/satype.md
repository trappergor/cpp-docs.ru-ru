---
title: satype (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.satype
helpviewer_keywords:
- satype attribute
ms.assetid: 1716590b-6bcb-4aba-b1bc-82f7335f02c3
ms.openlocfilehash: 7588e8d855d648309c46d981898cfbbf7888f4c9
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59025728"
---
# <a name="satype"></a>satype

Указывает тип данных `SAFEARRAY` структуры.

## <a name="syntax"></a>Синтаксис

```cpp
[ satype(data_type) ]
```

### <a name="parameters"></a>Параметры

*data_type*<br/>
Тип данных для `SAFEARRAY` структура данных, которая передается как параметр метода интерфейса.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Параметр интерфейса, метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

## <a name="remarks"></a>Примечания

**Satype** C++ атрибут указывает тип данных `SAFEARRAY`.

> [!NOTE]
> Уровень косвенности удаляется из `SAFEARRAY` указатель на созданного IDL-файла из как объявлено в CPP-файл.

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

## <a name="see-also"></a>См. также

[Атрибуты компилятора](compiler-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[id](id.md)