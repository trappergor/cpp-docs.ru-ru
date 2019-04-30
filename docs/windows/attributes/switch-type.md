---
title: switch_type (C++ атрибут COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.switch_type
helpviewer_keywords:
- switch_type attribute
ms.assetid: e24544dc-b3bc-48ae-b249-f967db49271e
ms.openlocfilehash: b461769d3d988efae0be7380e1e0112e3f3cf801
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407124"
---
# <a name="switchtype"></a>switch_type

Определяет тип переменной, которая используется в качестве объединения дискриминантный.

## <a name="syntax"></a>Синтаксис

```cpp
[switch_type(
type
}]
```

### <a name="parameters"></a>Параметры

*type*<br/>
Тип коммутатора, может быть целое число, символ, логическое значение или перечисления типа.

## <a name="remarks"></a>Примечания

**Switch_type** C++ атрибут имеет ту же функциональность, что [switch_type](/windows/desktop/Midl/switch-type) описании атрибута MIDL.

Атрибуты C++ не поддерживают [инкапсулированные объединения](/windows/desktop/Midl/encapsulated-unions). [Nonencapsulated объединения](/windows/desktop/Midl/nonencapsulated-unions) поддерживаются только в следующей форме:

```cpp
// cpp_attr_ref_switch_type.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLibrary")];
[ export ]
struct SizedValue2 {
   [switch_type("char"), switch_is(kind)] union {
      [case(1), string]
         wchar_t* wval;
      [default, string]
         char* val;
   };
   char kind;
};
```

## <a name="example"></a>Пример

См. в разделе [случай](case-cpp.md) пример для использовать **switch_type**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**typedef**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[export](export.md)