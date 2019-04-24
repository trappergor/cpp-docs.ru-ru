---
title: helpstringdll (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpstringdll
helpviewer_keywords:
- helpstringdll attribute [C++]
ms.assetid: 121271fa-f061-492b-b87f-bbfcf4b02e7b
ms.openlocfilehash: 72f5926018e3ac7ec4770f83d7a2c3438b67d861
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59025209"
---
# <a name="helpstringdll"></a>helpstringdll

Указывает имя библиотеки DLL для выполнения уточняющего запроса строки документа (локализации).

## <a name="syntax"></a>Синтаксис

```cpp
[ helpstringdll("string") ]
```

### <a name="parameters"></a>Параметры

*string*<br/>
Библиотека DLL, чтобы использовать для выполнения уточняющего запроса строки документа.

## <a name="remarks"></a>Примечания

**Helpstringdll** атрибут C++ имеет ту же функциональность, что [helpstringdll](/windows/desktop/Midl/helpstringdll) описании атрибута MIDL.

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
|**Применение**|**Класс**, **интерфейс**, метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)