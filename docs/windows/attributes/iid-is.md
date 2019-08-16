---
title: iid_is (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.iid_is
helpviewer_keywords:
- iid_is attribute
ms.assetid: 2f9b42a9-7130-4b08-9b1e-0d5d360e10ff
ms.openlocfilehash: 8bfa20f55afd85019795fdd40548158c2f49e126
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514660"
---
# <a name="iid_is"></a>iid_is

Указывает идентификатор IID COM-интерфейса, на который указывает указатель интерфейса.

## <a name="syntax"></a>Синтаксис

```cpp
[ iid_is("expression") ]
```

### <a name="parameters"></a>Параметры

*expression*<br/>
Выражение языка C, указывающее идентификатор IID COM-интерфейса, на который указывает указатель интерфейса.

## <a name="remarks"></a>Примечания

Атрибут **iid_is** C++ имеет те же функциональные возможности, что и атрибут [iid_is](/windows/win32/Midl/iid-is) MIDL.

## <a name="example"></a>Пример

В следующем коде показано использование **iid_is**:

```cpp
// cpp_attr_ref_iid_is.cpp
// compile with: /LD
#include "wtypes.h"
#include "unknwn.h"
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl : IDispatch
{
   [id(1)] HRESULT CreateInstance([in] REFIID riid,[out, iid_is("riid")]
   IUnknown ** ppvObject);
};

[module(name="ATLFIRELib")];
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|Параметр интерфейса, член данных|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Отсутствуют|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)