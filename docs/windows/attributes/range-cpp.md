---
title: Range (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.range
helpviewer_keywords:
- range attribute
ms.assetid: f352f79e-ecb3-4cdd-9cdd-8406ef473594
ms.openlocfilehash: d1221192eb1813d759f293fe5555d7aaa5b367ab
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514139"
---
# <a name="range-c"></a>range (C++)

Задает диапазон допустимых значений для аргументов или полей, значения которых задаются во время выполнения.

## <a name="syntax"></a>Синтаксис

```cpp
[ range(low, high) ]
```

### <a name="parameters"></a>Параметры

*low*<br/>
Значение нижнего диапазона.

*high*<br/>
Большое значение диапазона.

## <a name="remarks"></a>Примечания

Атрибут **Range** C++ имеет те же функциональные возможности, что и атрибут [Range](/windows/win32/Midl/range) MIDL.

## <a name="example"></a>Пример

```cpp
// cpp_attr_ref_range.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]
__interface ICustom {
   HRESULT Custom([in] long l, [out, retval] long *pLong);
   HRESULT length_is1([in, range(0, 999)] long f, [in, length_is(f)] char array[10]);
   HRESULT length_is2([in, range(-99, -1)] long f, [in, length_is("f"), size_is(10)] char *array);
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|Метод интерфейса, параметр интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Отсутствуют|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)<br/>
[Атрибуты элементов данных](data-member-attributes.md)