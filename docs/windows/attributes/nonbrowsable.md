---
title: недоступный дляC++ просмотра (атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.nonbrowsable
helpviewer_keywords:
- nonbrowsable attribute
ms.assetid: e71a98e7-4b65-454a-9829-342b9f2a84be
ms.openlocfilehash: f0aae070c1c97695180797b228178b210493b7bb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166566"
---
# <a name="nonbrowsable"></a>nonbrowsable

Указывает, что член интерфейса не должен отображаться в обозревателе свойств.

## <a name="syntax"></a>Синтаксис

```cpp
[nonbrowsable]
```

## <a name="remarks"></a>Remarks

**Неотображаемый** C++ атрибут имеет те же функциональные возможности, что и [неотображаемый](/windows/win32/Midl/nonbrowsable) атрибут MIDL.

## <a name="example"></a>Пример

```cpp
// cpp_attr_ref_nonbrowsable.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[object, helpstring("help string"), helpstringcontext(1),
uuid="11111111-1111-1111-1111-111111111111"]
__interface IMyI
{
   [nonbrowsable] HRESULT xx();
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
[Атрибуты метода](method-attributes.md)
