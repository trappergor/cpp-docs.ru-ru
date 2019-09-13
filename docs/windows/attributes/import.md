---
title: Import (C++ атрибут com)
ms.date: 10/03/2018
f1_keywords:
- vc-attr.import
helpviewer_keywords:
- import attribute
ms.assetid: ebf07cae-39fb-4047-8b57-54af0a9a83de
ms.openlocfilehash: f9ed80bdcc04302c0dee85935f377c8e3dbfd37f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514618"
---
# <a name="import"></a>импорт

Указывает другой файл. idl,. odl или заголовок, содержащий определения, на которые вы хотите создать ссылку из основного IDL.

## <a name="syntax"></a>Синтаксис

```cpp
[ import(
   idl_file
) ];
```

### <a name="parameters"></a>Параметры

*idl_file*<br/>
Имя IDL-файла, который необходимо импортировать в библиотеку типов текущего проекта.

## <a name="remarks"></a>Примечания

Атрибут **Import** C++ приводит к тому, что `import "docobj.idl"` инструкциябудетпомещенаподинструкциейвсозданномIDL-файле.`#import` Атрибут **Import** имеет те же функциональные возможности, что и атрибут [Import](/windows/win32/Midl/import) MIDL.

Атрибут **Import** помещает указанный файл в IDL-файл, который будет создан проектом. атрибут **Import** не позволяет вызывать конструкции в указанном файле из исходного кода в проекте.  Чтобы вызвать конструкции в указанном файле из исходного кода в проекте, используйте [#import](../../preprocessor/hash-import-directive-cpp.md) и `embedded_idl` атрибут или включите h-файл для *idl_file*, если файл. h существует.

## <a name="example"></a>Пример

В приведенном ниже коде

```cpp
// cpp_attr_ref_import.cpp
// compile with: /LD
[module(name="MyLib")];
[import(import.idl)];
```

создает следующий код в созданном IDL-файле:

```
import "docobj.idl";
import "import.idl";

[ uuid(EED3644C-8488-3ECD-BA97-147DB3CDB499), version(1.0) ]
library MyLib {
   importlib("stdole2.tlb");
   importlib("olepro32.dll");
...
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
[importidl](importidl.md)<br/>
[importlib](importlib.md)<br/>
[include](include-cpp.md)<br/>
[includelib](includelib-cpp.md)