---
title: call_as (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.call_as
helpviewer_keywords:
- call_as attribute
ms.assetid: a09d7f1f-353b-4870-9b45-f0284161695d
ms.openlocfilehash: 755741faec6c0ba702d372ca8dee486edcb72ef3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167342"
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

## <a name="remarks"></a>Remarks

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
|**Применение**|Метод интерфейса|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[local](local-cpp.md)
