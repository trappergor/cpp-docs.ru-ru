---
title: источник (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.source
helpviewer_keywords:
- source attribute
ms.assetid: 1878d05d-7709-4e97-b114-c62f38f5140e
ms.openlocfilehash: 699ea64de49a4383bc8fb62b2f3b2133d7c496c9
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59030249"
---
# <a name="source-c"></a>source (C++)

В классе, задает интерфейсы COM-объекта источника для точек подключения. На свойства или метода указывает, что член возвращает объект или переменная типа VARIANT, являющейся источником событий.

## <a name="syntax"></a>Синтаксис

```cpp
[ source(interfaces) ]
```

### <a name="parameters"></a>Параметры

*интерфейсы*<br/>
Один или несколько интерфейсов, укажите при применении исходного атрибута к классу. Этот параметр не используется, когда источника применяется к свойству или методу.

## <a name="remarks"></a>Примечания

**Источника** атрибут C++ имеет ту же функциональность, что [источника](/windows/desktop/Midl/source) описании атрибута MIDL.

Можно использовать [по умолчанию](default-cpp.md) атрибут для указания интерфейсе источника по умолчанию для объекта.

## <a name="example"></a>Пример

```cpp
// cpp_attr_ref_source.cpp
// compile with: /LD
#include "windows.h"
#include "unknwn.h"
[module(name="MyLib")];

[object, uuid(11111111-1111-1111-1111-111111111111)]
__interface b
{
   [id(0), propget, bindable, displaybind, defaultbind, requestedit]
   HRESULT get_I([out, retval]long *i);
};

[object, uuid(11111111-1111-1111-1111-111111111131)]
__interface c
{
   [id(0), propget, bindable, displaybind, defaultbind, requestedit]
   HRESULT et_I([out, retval]long *i);
};

[coclass, default(c), uuid(11111111-1111-1111-1111-111111111132)]
class N : public b
{
};

[coclass, source(c), default(b, c), uuid(11111111-1111-1111-1111-111111111133)]
class NN : public b
{
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**Класс**, **структуры**, **интерфейс**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|`coclass` (когда применимы к классам или структурам)|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[кокласс](coclass.md)