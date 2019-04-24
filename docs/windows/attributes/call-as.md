---
title: call_as (C++ атрибут COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.call_as
helpviewer_keywords:
- call_as attribute
ms.assetid: a09d7f1f-353b-4870-9b45-f0284161695d
ms.openlocfilehash: a0051cdca6673800b37d5733c0b849da24010fcb
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59023923"
---
# <a name="callas"></a>call_as

Позволяет [локального](local-cpp.md) функции для сопоставления с удаленной функции так, что при вызове удаленной функции локальной функции.

## <a name="syntax"></a>Синтаксис

```cpp
[ call_as(function) ]
```

### <a name="parameters"></a>Параметры

*function*<br/>
Локальная функция, которую требуется вызывать при вызове удаленной функции.

## <a name="remarks"></a>Примечания

**Call_as** C++ атрибут имеет ту же функциональность, что [call_as](/windows/desktop/Midl/call-as) описании атрибута MIDL.

## <a name="example"></a>Пример

В следующем коде показано, как можно использовать **call_as** для сопоставления функции не поддерживающие удаленное взаимодействие (`f1`) функции удаленного взаимодействия (`Remf1`):

```cpp
// cpp_attr_ref_call_as.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyLib")];
[dual, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMInterface {
   [local] HRESULT f1 ( int i );
   [call_as(f1)] HRESULT Remf1 ( int i );
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[local](local-cpp.md)