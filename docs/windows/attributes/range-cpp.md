---
title: диапазон (атрибут COM C++) | Документация Майкрософт
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.range
dev_langs:
- C++
helpviewer_keywords:
- range attribute
ms.assetid: f352f79e-ecb3-4cdd-9cdd-8406ef473594
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 593cfbd4b7430c3f6ac5b4f2ab1053665136ab25
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791160"
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

Дополнительные сведения о контекстах атрибутов см. в разделе [контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)<br/>
[Атрибуты элементов данных](data-member-attributes.md)  