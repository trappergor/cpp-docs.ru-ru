---
title: диапазон (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.range
helpviewer_keywords:
- range attribute
ms.assetid: f352f79e-ecb3-4cdd-9cdd-8406ef473594
ms.openlocfilehash: 9ce941fe95f2bbef3895c039984db1e1d2985ae1
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59029542"
---
# <a name="range-c"></a>range (C++)

Указывает диапазон допустимых значений для полей, значения которых устанавливаются во время выполнения и аргументы.

## <a name="syntax"></a>Синтаксис

```cpp
[ range(low, high) ]
```

### <a name="parameters"></a>Параметры

*low*<br/>
Значение нижняя граница диапазона.

*high*<br/>
Значение верхняя граница диапазона.

## <a name="remarks"></a>Примечания

**Диапазон** атрибут C++ имеет ту же функциональность, что [диапазон](/windows/desktop/Midl/range) описании атрибута MIDL.

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
|**Применение**|Метод интерфейса, параметр интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)<br/>
[Атрибуты элементов данных](data-member-attributes.md)