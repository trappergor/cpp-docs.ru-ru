---
title: несоздаваемый (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.noncreatable
helpviewer_keywords:
- noncreatable attribute
ms.assetid: 4d17937b-0bff-41af-ba57-53e18b7ab5a9
ms.openlocfilehash: e855497cb6f619ecdaa6aedf16a04f045a60faa7
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514562"
---
# <a name="noncreatable"></a>noncreatable

Определяет объект, который не может быть создан самим по себе.

## <a name="syntax"></a>Синтаксис

```cpp
[noncreatable]
```

## <a name="remarks"></a>Примечания

**Несоздаваемый** C++ атрибут имеет те же функциональные возможности, что и [несоздаваемый](/windows/win32/Midl/noncreatable) атрибут MIDL, и автоматически передается в созданный объект. IDL-файл компилятором.

Если этот атрибут используется в проекте, использующем ATL, поведение атрибута изменяется. В дополнение к описанному выше поведению, атрибут также внедряет макрос [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) . Этот макрос указывает ATL, что объект не может быть создан извне.

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
|**Относится к**|**класс**, **Структура**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|**кокласс**|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)
