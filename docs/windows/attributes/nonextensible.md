---
title: нерасширяемыйC++ (атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.nonextensible
helpviewer_keywords:
- nonextensible attribute
ms.assetid: c7ef1554-809f-4ea0-a7cd-dc7786d40c3e
ms.openlocfilehash: 2a1cd4d685e2fd141c6e11feaea488f44a884c80
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214699"
---
# <a name="nonextensible"></a>nonextensible

Указывает, что реализация `IDispatch` включает только свойства и методы, перечисленные в описании интерфейса, и не может быть расширена с помощью дополнительных элементов во время выполнения.

## <a name="syntax"></a>Синтаксис

```cpp
[nonextensible]
```

## <a name="remarks"></a>Remarks

**Нерасширяемый** C++ атрибут имеет те же функциональные возможности, что и [нерасширяемый](/windows/win32/Midl/nonextensible) атрибут MIDL.

Для использования **нерасширяемости** также требуется атрибут [oleautomation](oleautomation.md) .

## <a name="example"></a>Пример

В следующем коде показано одно использование **нерасширяемого** атрибута:

```cpp
// cpp_attr_ref_nonextensible.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];
[export] typedef long HRESULT;

[dual, nonextensible, ms_union, oleautomation,
uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl
{
   HRESULT procedure (int i);
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**interface**|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|`dual` и `oleautomation`или `dispinterface`|
|**Недопустимые атрибуты**|None|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)
