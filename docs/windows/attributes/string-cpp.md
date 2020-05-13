---
title: String (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.string
helpviewer_keywords:
- string attribute
ms.assetid: ddde900a-2e99-4fcd-86e8-57e1bdba7c93
ms.openlocfilehash: 96d5e609130b34a4a5f35109ce691c2de470e537
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166168"
---
# <a name="string-c"></a>string (C++)

Указывает, что одномерный массив **char**, **wchar_t**, `byte` (или эквивалентный) или указатель на такой массив должен рассматриваться как строка.

## <a name="syntax"></a>Синтаксис

```cpp
[string]
```

## <a name="remarks"></a>Remarks

Атрибут **String** C++ имеет те же функциональные возможности, что и атрибут [String](/windows/win32/Midl/string) MIDL.

## <a name="example"></a>Пример

В следующем коде показано, как использовать **строку** в интерфейсе и в определении типа:

```cpp
// cpp_attr_ref_string.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];
[export, string] typedef char a[21];
[dispinterface, restricted, uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl
{
   [id(1)] HRESULT Method3([in, string] char *pC);
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Массив или указатель на массив, параметр интерфейса, метод интерфейса|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты массивов](array-attributes.md)<br/>
[export](export.md)
