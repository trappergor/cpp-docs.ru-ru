---
title: helpstringcontext (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpstringcontext
helpviewer_keywords:
- helpstringcontext attribute [C++]
ms.assetid: d4cd135e-d91c-4aa3-9353-8aeb096f52cf
ms.openlocfilehash: d292dd53ff3009a571dd5b0a1ba102e75b648e4d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533605"
---
# <a name="helpstringcontext"></a>helpstringcontext

Указывает идентификатор раздела справки в файл с расширением .hlp или .chm.

## <a name="syntax"></a>Синтаксис

```cpp
[ helpstringcontext(contextID) ]
```

### <a name="parameters"></a>Параметры

*contextID*<br/>
В 32-разрядный идентификатор контекста справки в **помочь** файл.

## <a name="remarks"></a>Примечания

**Helpstringcontext** атрибут C++ имеет ту же функциональность, что [helpstringcontext](/windows/desktop/Midl/helpstringcontext) ODL-атрибут.

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
|**Применение**|**Класс**, **интерфейс**, метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[module](module-cpp.md)