---
title: аппобжект (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.appobject
helpviewer_keywords:
- appobject attribute
ms.assetid: 8ce30b73-e945-403e-a755-6bc78078a695
ms.openlocfilehash: ebbb3ce71dc9b947ef49a42ee41a5ce2d5abbb34
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168516"
---
# <a name="appobject"></a>appobject

Определяет компонент в качестве объекта приложения, связанного с полным exe-приложением, и указывает, что функции и свойства компонентного класса глобально доступны в этой [библиотеке типов](../../mfc/automation-clients-using-type-libraries.md).

## <a name="syntax"></a>Синтаксис

```cpp
[appobject]
```

## <a name="remarks"></a>Remarks

Атрибут **аппобжект** C++ имеет те же функциональные возможности, что и атрибут [аппобжект](/windows/win32/Midl/appobject) MIDL.

## <a name="example"></a>Пример

В следующем коде показано определение простого класса, начинающееся с блока атрибутов, который включает **аппобжект**:

```cpp
// cpp_attr_ref_appobject.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib", uuid="f1ce17f0-a5df-4d26-95f6-0a122197ac5b")];

[object, uuid="905de6db-7a12-45ab-9f8b-b39f5112f010"]
__interface ICustom {};

[coclass, appobject,uuid="00395340-745f-4b69-bd58-e2921452b9fc"]
class A : public ICustom {
   int i;
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**класс**, **Структура**|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|`coclass`|
|**Недопустимые атрибуты**|None|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)
