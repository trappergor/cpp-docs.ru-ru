---
title: хелпстрингдлл (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpstringdll
helpviewer_keywords:
- helpstringdll attribute [C++]
ms.assetid: 121271fa-f061-492b-b87f-bbfcf4b02e7b
ms.openlocfilehash: 4ec0d959b2fc10fc34bfc7050a1970359dae5bbc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168126"
---
# <a name="helpstringdll"></a>helpstringdll

Указывает имя библиотеки DLL, используемой для поиска строки документа (локализация).

## <a name="syntax"></a>Синтаксис

```cpp
[ helpstringdll("string") ]
```

### <a name="parameters"></a>Параметры

*строка*<br/>
Библиотека DLL, используемая для поиска строки документа.

## <a name="remarks"></a>Remarks

Атрибут **хелпстрингдлл** C++ имеет те же функциональные возможности, что и атрибут [хелпстрингдлл](/windows/win32/Midl/helpstringdll) MIDL.

## <a name="example"></a>Пример

```cpp
// cpp_attr_ref_helpstringdll.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib", helpstringdll="xx.dll")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI
{
   HRESULT xxx();
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**класс**, **интерфейс**, метод интерфейса|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)
