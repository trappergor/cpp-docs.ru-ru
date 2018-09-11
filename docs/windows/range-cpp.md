---
title: диапазон (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: a4f84684c5d8f8feb8595da628976c90a2593c96
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43201355"
---
# <a name="range-c"></a>range (C++)

Указывает диапазон допустимых значений для полей, значения которых устанавливаются во время выполнения и аргументы.

## <a name="syntax"></a>Синтаксис

```cpp
[ range(
   low,
   high
) ]
```

### <a name="parameters"></a>Параметры

*low*  
Значение нижняя граница диапазона.

*high*  
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

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)  
[Атрибуты метода](../windows/method-attributes.md)  
[Атрибуты параметра](../windows/parameter-attributes.md)  
[Атрибуты элементов данных](../windows/data-member-attributes.md)  