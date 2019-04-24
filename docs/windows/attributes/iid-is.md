---
title: iid_is (C++ атрибут COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.iid_is
helpviewer_keywords:
- iid_is attribute
ms.assetid: 2f9b42a9-7130-4b08-9b1e-0d5d360e10ff
ms.openlocfilehash: b91fb7937bb0e20f2500eace9695bc0ddba21b26
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59038561"
---
# <a name="iidis"></a>iid_is

Указывает идентификатор IID интерфейса COM, на которые указывает указатель интерфейса.

## <a name="syntax"></a>Синтаксис

```cpp
[ iid_is("expression") ]
```

### <a name="parameters"></a>Параметры

*Выражение*<br/>
Выражение языка C, которое указывает IID COM-интерфейса, на который указывает указатель интерфейса.

## <a name="remarks"></a>Примечания

**Iid_is** C++ атрибут имеет ту же функциональность, что [iid_is](/windows/desktop/Midl/iid-is) описании атрибута MIDL.

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
|**Применение**|Параметр интерфейса, элемент данных|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)