---
title: несоздаваемый (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.noncreatable
helpviewer_keywords:
- noncreatable attribute
ms.assetid: 4d17937b-0bff-41af-ba57-53e18b7ab5a9
ms.openlocfilehash: c5d51d7c5628a875f036b4e48b03b317490b37ff
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224400"
---
# <a name="noncreatable"></a>noncreatable

Определяет объект, который не может быть создан самим по себе.

## <a name="syntax"></a>Синтаксис

```cpp
[noncreatable]
```

## <a name="remarks"></a>Remarks

**Несоздаваемый** атрибут C++ имеет те же функциональные возможности, что и [несоздаваемый](/windows/win32/Midl/noncreatable) атрибут MIDL, и автоматически передается в созданный объект. IDL-файл компилятором.

Если этот атрибут используется в проекте, использующем ATL, поведение атрибута изменяется. В дополнение к описанному выше поведению, атрибут также внедряет [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) макрос. Этот макрос указывает ATL, что объект не может быть создан извне.

## <a name="example"></a>Пример

```cpp
// cpp_attr_ref_noncreatable.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[object, uuid("11111111-1111-1111-1111-111111111111")]
__interface A
{
};

[coclass, uuid("11111111-1111-1111-1111-111111111112"), noncreatable]
class CMyClass : public A
{
   HRESULT xx();
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|**`class`**, **`struct`**|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|**кокласс**|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также статью

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты класса](class-attributes.md)
