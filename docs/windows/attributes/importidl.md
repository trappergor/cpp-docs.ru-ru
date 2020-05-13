---
title: импортидл (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.importidl
helpviewer_keywords:
- importidl attribute
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
ms.openlocfilehash: 6e41a98bef079c92b6df6e7eff203301aa9ceae4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166826"
---
# <a name="importidl"></a>importidl

Вставляет указанный IDL-файл в созданный IDL-файл.

## <a name="syntax"></a>Синтаксис

```cpp
[ importidl(idl_file) ];
```

### <a name="parameters"></a>Параметры

*idl_file*<br/>
Определяет имя IDL-файла, который необходимо объединить с IDL-файлом, который будет создан для приложения.

## <a name="remarks"></a>Remarks

Атрибут **импортидл** C++ помещает раздел за пределами блока библиотеки (в *idl_file*) в созданный IDL-файл программы и раздел библиотеки (в *idl_file*) в раздел Library созданного idl-файла программы.

Можно использовать **импортидл**, например, если вы хотите использовать idl-файл с собственной кодировкой с созданным файлом IDL.

## <a name="example"></a>Пример

```cpp
// cpp_attr_ref_importidl.cpp
// compile with: /LD
[module(name="MyLib")];
[importidl("import.idl")];
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

[Атрибуты компилятора](compiler-attributes.md)<br/>
[Изолированные атрибуты](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importlib](importlib.md)<br/>
[include](include-cpp.md)<br/>
[includelib](includelib-cpp.md)
