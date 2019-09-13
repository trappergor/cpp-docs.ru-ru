---
title: Источник (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.source
helpviewer_keywords:
- source attribute
ms.assetid: 1878d05d-7709-4e97-b114-c62f38f5140e
ms.openlocfilehash: 79614a345e6c07b03df351da93a847fe12e4b110
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514023"
---
# <a name="source-c"></a>source (C++)

В классе указывает исходные интерфейсы COM-объекта для точек соединения. В свойстве или методе указывает, что член возвращает объект или вариант, являющийся источником событий.

## <a name="syntax"></a>Синтаксис

```cpp
[ source(interfaces) ]
```

### <a name="parameters"></a>Параметры

*interfaces*<br/>
Один или несколько интерфейсов, которые указываются при применении атрибута Source к классу. Этот параметр не используется, если источник применяется к свойству или методу.

## <a name="remarks"></a>Примечания

**Исходный** C++ атрибут имеет те же функциональные возможности, что и [Исходный](/windows/win32/Midl/source) атрибут MIDL.

Можно использовать атрибут [по умолчанию](default-cpp.md) , чтобы указать исходный интерфейс по умолчанию для объекта.

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
|**Относится к**|**класс**, **Структура**, **интерфейс**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|`coclass`(при применении к классу или структуре)|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[кокласс](coclass.md)