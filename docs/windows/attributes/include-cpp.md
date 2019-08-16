---
title: включить (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.include
helpviewer_keywords:
- include attribute
ms.assetid: d23f8b91-fe5b-48fa-9371-8bd73af7b8e3
ms.openlocfilehash: ece88ebd7b5d9d81beb871427b58a72b2cf02022
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514552"
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

## <a name="remarks"></a>Примечания

Атрибут **include** C++ приводит к тому, что `import "docobj.idl"` инструкциябудетпомещенаподинструкциейвсозданномIDL-файле.`#include`

Атрибут **include** C++ имеет те же функциональные возможности, что и атрибут [include](/windows/win32/Midl/include) в формате MIDL.

## <a name="example"></a>Пример

В следующем коде показан пример использования **include**. В этом примере файл include. h содержит только `#include` инструкцию.

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
|**Относится к**|В любом месте|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Отсутствуют|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Изолированные атрибуты](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[includelib](includelib-cpp.md)<br/>
[importlib](importlib.md)