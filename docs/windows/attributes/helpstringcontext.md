---
title: хелпстрингконтекст (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpstringcontext
helpviewer_keywords:
- helpstringcontext attribute [C++]
ms.assetid: d4cd135e-d91c-4aa3-9353-8aeb096f52cf
ms.openlocfilehash: ae48c6216b1f1d987b33eff50acf9d82dc551400
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501493"
---
# <a name="helpstringcontext"></a>helpstringcontext

Указывает идентификатор раздела справки в файле. hlp или. chm.

## <a name="syntax"></a>Синтаксис

```cpp
[ helpstringcontext(contextID) ]
```

### <a name="parameters"></a>Параметры

*contextID*<br/>
32-разрядный идентификатор контекста справки в файле **справки** .

## <a name="remarks"></a>Примечания

Атрибут **хелпстрингконтекст** C++ имеет те же функциональные возможности, что и атрибут [хелпстрингконтекст](/windows/win32/Midl/helpstringcontext) ODL.

## <a name="example"></a>Пример

```cpp
// cpp_attr_ref_helpstringcontext.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[   object, helpstring("help string"), helpstringcontext(1), uuid="11111111-1111-1111-1111-111111111111"
]
__interface IMyI
{
   HRESULT xx();
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|**класс**, **интерфейс**, метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Отсутствуют|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[module](module-cpp.md)