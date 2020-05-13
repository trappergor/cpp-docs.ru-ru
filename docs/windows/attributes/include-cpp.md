---
title: включить (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.include
helpviewer_keywords:
- include attribute
ms.assetid: d23f8b91-fe5b-48fa-9371-8bd73af7b8e3
ms.openlocfilehash: 39f991bb036dce1c50a9d2ee800d3fec65af7c55
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166787"
---
# <a name="include-c"></a>include (C++)

Указывает один или несколько файлов заголовков для включения в созданный IDL-файл.

## <a name="syntax"></a>Синтаксис

```cpp
[ include(header_file) ];
```

### <a name="parameters"></a>Параметры

*header_file*<br/>
Имя файла, который необходимо добавить в созданный IDL-файл.

## <a name="remarks"></a>Remarks

Атрибут **include** C++ приводит к тому, что `#include` оператор помещается под инструкцией `import "docobj.idl"` в созданном IDL-файле.

Атрибут **include** C++ имеет те же функциональные возможности, что и атрибут [include](/windows/win32/Midl/include) в формате MIDL.

## <a name="example"></a>Пример

В следующем коде показан пример использования **include**. В этом примере файл include. h содержит только инструкцию `#include`.

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
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Изолированные атрибуты](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[includelib](includelib-cpp.md)<br/>
[importlib](importlib.md)
