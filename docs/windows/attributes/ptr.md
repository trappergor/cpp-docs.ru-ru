---
title: PTR (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.ptr
helpviewer_keywords:
- ptr attribute
ms.assetid: 95eaea57-a5be-45f6-a612-ba2c9bc4645a
ms.openlocfilehash: 9e45cd529562fe238f96f98cf7f91e15df34270a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224387"
---
# <a name="ptr"></a>ptr

Назначает указатель в качестве полного указателя.

## <a name="syntax"></a>Синтаксис

```cpp
[ptr]
```

## <a name="remarks"></a>Remarks

Атрибут **ptr** C++ имеет те же функциональные возможности, что и атрибут [ptr](/windows/win32/Midl/ptr) MIDL.

## <a name="example"></a>Пример

См. пример для [DefaultValue](defaultvalue.md) для примера использования **ptr**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|Параметр интерфейса, метод интерфейса,**`typedef`**|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также статью

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[Атрибуты typedef, enum, Union и struct](typedef-enum-union-and-struct-attributes.md)
