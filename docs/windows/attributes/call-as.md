---
title: call_as (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.call_as
helpviewer_keywords:
- call_as attribute
ms.assetid: a09d7f1f-353b-4870-9b45-f0284161695d
ms.openlocfilehash: f36cf8d1be589cc614a6def583b00af00aabdb61
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501798"
---
# <a name="call_as"></a>call_as

Позволяет сопоставить [локальную](local-cpp.md) функцию с удаленной функцией, чтобы при вызове удаленной функции вызывалась локальная функция.

## <a name="syntax"></a>Синтаксис

```cpp
[ call_as(function) ]
```

### <a name="parameters"></a>Параметры

*function*<br/>
Локальная функция, которая должна вызываться при вызове удаленной функции.

## <a name="remarks"></a>Примечания

Атрибут **call_as** C++ имеет те же функциональные возможности, что и атрибут [call_as](/windows/win32/Midl/call-as) MIDL.

## <a name="example"></a>Пример

В следующем коде показано, как можно использовать **call_as** для преобразования функции, не поддерживающей удаленное взаимодействие (`f1`), в удаленную функцию (`Remf1`):

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
|**Относится к**|Метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Отсутствуют|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[local](local-cpp.md)