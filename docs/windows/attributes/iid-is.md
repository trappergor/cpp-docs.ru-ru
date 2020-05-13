---
title: iid_is (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.iid_is
helpviewer_keywords:
- iid_is attribute
ms.assetid: 2f9b42a9-7130-4b08-9b1e-0d5d360e10ff
ms.openlocfilehash: 627ecff4835386dc70a9f3dfac0500404a84eefe
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167996"
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

## <a name="remarks"></a>Remarks

Атрибут **iid_is** C++ имеет те же функциональные возможности, что и атрибут [iid_is](/windows/win32/Midl/iid-is) MIDL.

## <a name="example"></a>Пример

В следующем коде показано использование **iid_is**.

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
|**Применение**|Параметр интерфейса, член данных|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)
