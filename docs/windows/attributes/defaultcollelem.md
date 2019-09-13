---
title: defaultcollelem
ms.date: 10/02/2018
f1_keywords:
- vc-attr.defaultcollelem
helpviewer_keywords:
- defaultcollelem attribute
ms.assetid: 3dbbd293-8b83-4f70-a36b-64cc1d0b6713
ms.openlocfilehash: c8848562c1470198d3f2a1b6f285510bcbb43d7c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501654"
---
# <a name="defaultcollelem"></a>defaultcollelem

Используется для Visual Basic оптимизации кода.

## <a name="syntax"></a>Синтаксис

```cpp
[defaultcollelem]
```

## <a name="remarks"></a>Примечания

Атрибут **дефаултколлелем** C++ имеет те же функциональные возможности, что и атрибут [дефаултколлелем](/windows/win32/Midl/defaultcollelem) MIDL.

## <a name="example"></a>Пример

В следующем коде показан метод интерфейса с использованием атрибута **дефаултколлелем** :

```cpp
// cpp_attr_ref_defaultcollelem.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];
[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyForm
{
   [propget, id(1), bindable, defaultcollelem, displaybind, defaultbind, requestedit] HRESULT P1([out, retval] long *nSize);
   [propput, id(1), bindable, defaultcollelem, displaybind, defaultbind, requestedit] HRESULT P1([in] long nSize);
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|Метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Отсутствуют|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)