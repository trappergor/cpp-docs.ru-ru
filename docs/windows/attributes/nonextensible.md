---
title: нерасширяемыйC++ (атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.nonextensible
helpviewer_keywords:
- nonextensible attribute
ms.assetid: c7ef1554-809f-4ea0-a7cd-dc7786d40c3e
ms.openlocfilehash: f2947e223d068ea6cc92a41abe19cb7f920112b2
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514393"
---
# <a name="nonextensible"></a>nonextensible

Указывает, что `IDispatch` реализация включает только свойства и методы, перечисленные в описании интерфейса, и не может быть расширена с помощью дополнительных элементов во время выполнения.

## <a name="syntax"></a>Синтаксис

```cpp
[nonextensible]
```

## <a name="remarks"></a>Примечания

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
|**Относится к**|**interface**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|`dual`и `oleautomation`, или`dispinterface`|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)