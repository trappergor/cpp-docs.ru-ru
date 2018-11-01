---
title: Включить (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.include
helpviewer_keywords:
- include attribute
ms.assetid: d23f8b91-fe5b-48fa-9371-8bd73af7b8e3
ms.openlocfilehash: 6fb385877285602c1eb6649d11e16558d7fb07ec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544759"
---
# <a name="include-c"></a>include (C++)

Указывает один или несколько файлов заголовка для включения в созданного IDL-файла.

## <a name="syntax"></a>Синтаксис

```cpp
[ include(header_file) ];
```

### <a name="parameters"></a>Параметры

*HEADER_FILE*<br/>
Имя файла, который будет включен в созданного IDL-файла.

## <a name="remarks"></a>Примечания

**Включают** C++ атрибут приводит к `#include` инструкцию, чтобы помещаться под `import "docobj.idl"` инструкции в созданного IDL-файла.

**Включают** атрибут C++ имеет ту же функциональность, что [включают](/windows/desktop/Midl/include) описании атрибута MIDL.

## <a name="example"></a>Пример

Ниже показан пример использования **включают**. В этом примере include.h файл содержит только `#include` инструкции.

```cpp
// cpp_attr_ref_include.cpp
// compile with: /LD
[module(name="MyLib")];
[include(cpp_attr_ref_include.h)];
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|В любом месте|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Изолированные атрибуты](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[includelib](includelib-cpp.md)<br/>
[importlib](importlib.md)