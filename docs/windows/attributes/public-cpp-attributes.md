---
title: Public (C++ атрибуты) (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.public
helpviewer_keywords:
- public attribute
ms.assetid: c42e1fd5-6cb1-48fe-8a03-95f2a2e0137c
ms.openlocfilehash: 274af011f2d61521885e93d4ce1eddad149748ad
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514173"
---
# <a name="public-c-attributes"></a>public (атрибуты C++)

Гарантирует, что typedef перейдет в библиотеку типов, даже если на него нет ссылок из IDL-файла.

## <a name="syntax"></a>Синтаксис

```cpp
[public]
```

## <a name="remarks"></a>Примечания

Атрибут **Public** C++ имеет те же функциональные возможности, что и [открытый](/windows/win32/Midl/public) атрибут MIDL.

## <a name="example"></a>Пример

В следующем коде показано, как использовать атрибут **Public** :

```cpp
// cpp_attr_ref_public.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];
[export, public] typedef long MEMBERID;

[dispinterface, uuid(99999999-9999-9999-9999-000000000000)]
__interface IFireTabCtrl : IDispatch
{
   [id(2)] long procedure ([in, optional] VARIANT i);
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|**typedef**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Отсутствуют|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)