---
title: Импорт | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.import
dev_langs:
- C++
helpviewer_keywords:
- import attribute
ms.assetid: ebf07cae-39fb-4047-8b57-54af0a9a83de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a9e2ee577c3285a7e4c3db2fb19d934417bbe26d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411564"
---
# <a name="import"></a>импорт

Указывает другой файл .idl, .odl или заголовок, содержащий определения, которые нужно сделать ссылку из вашего основного языка IDL.

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

**Импорта** C++ атрибут приводит к `#import` инструкцию, чтобы помещаться под `import "docobj.idl"` инструкции в созданного IDL-файла. **Импорта** атрибут имеет ту же функциональность, что [импорта](/windows/desktop/Midl/import) описании атрибута MIDL.

**Импорта** атрибут только помещает указанный файл в IDL-файл, который будет создаваться в проекте; **импорта** атрибут не позволяет вызывать конструкции в указанный файл из исходного кода в проекте.  Чтобы вызвать конструкции в указанный файл из исходного кода в проекте, либо использовать [#import](../preprocessor/hash-import-directive-cpp.md) и `embedded_idl` атрибут или включить в h-файл для *idl_file*, если существует h-файл.

## <a name="example"></a>Пример

В приведенном ниже коде

```cpp
// cpp_attr_ref_import.cpp
// compile with: /LD
[module(name="MyLib")];
[import(import.idl)];
```

Создает следующий код в созданного IDL-файла:

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
|**Применение**|В любом месте|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)<br/>
[Изолированные атрибуты](../windows/stand-alone-attributes.md)<br/>
[importidl](../windows/importidl.md)<br/>
[importlib](../windows/importlib.md)<br/>
[include](../windows/include-cpp.md)<br/>
[includelib](../windows/includelib-cpp.md)  