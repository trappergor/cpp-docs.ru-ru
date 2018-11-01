---
title: defaultvtable (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.defaultvtable
helpviewer_keywords:
- defaultvtable attribute
ms.assetid: 5b3ed483-f69e-44dd-80fc-952028eb9d73
ms.openlocfilehash: 40f901345601193db9752ea6c6dca980ded0625d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579937"
---
# <a name="defaultvtable"></a>defaultvtable

Определяет интерфейс как интерфейс по умолчанию vtable для COM-объекта.

## <a name="syntax"></a>Синтаксис

```cpp
[ defaultvtable(interface) ]
```

### <a name="parameters"></a>Параметры

*interface*<br/>
Указанный интерфейс, который вы хотите иметь vtable по умолчанию для COM-объекта.

## <a name="remarks"></a>Примечания

**Defaultvtable** атрибут C++ имеет ту же функциональность, что [defaultvtable](/windows/desktop/Midl/defaultvtable) описании атрибута MIDL.

## <a name="example"></a>Пример

В следующем коде показано атрибуты для класса, используйте **defaultvtable** для указания интерфейс по умолчанию:

```cpp
// cpp_attr_ref_defaultvtable.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI1 {
   HRESULT x();
};

[object, uuid("00000000-0000-0000-0000-000000000002")]
__interface IMyI2 {
   HRESULT x();
};

[object, uuid("00000000-0000-0000-0000-000000000003")]
__interface IMyI3 {
   HRESULT x();
};

[coclass, source(IMyI3, IMyI1), default(IMyI3, IMyI2), defaultvtable(IMyI1),
uuid("00000000-0000-0000-0000-000000000004")]
class CMyC3 : public IMyI3 {};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**Класс**, **структуры**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|**кокласс**|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)