---
title: недоступная для просмотра (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.nonbrowsable
helpviewer_keywords:
- nonbrowsable attribute
ms.assetid: e71a98e7-4b65-454a-9829-342b9f2a84be
ms.openlocfilehash: 34b3c93b60009284897c4b7c1c29ceb4fefa2c49
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50592638"
---
# <a name="nonbrowsable"></a>nonbrowsable

Указывает, что член интерфейса не должен отображаться в обозревателе свойств.

## <a name="syntax"></a>Синтаксис

```cpp
[nonbrowsable]
```

## <a name="remarks"></a>Примечания

**Недоступная для просмотра** атрибут C++ имеет ту же функциональность, что [недоступная для просмотра](/windows/desktop/Midl/nonbrowsable) описании атрибута MIDL.

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
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)