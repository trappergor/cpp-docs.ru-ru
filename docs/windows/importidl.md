---
title: importidl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.importidl
dev_langs:
- C++
helpviewer_keywords:
- importidl attribute
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9406cc95804e4eb9fd76f53201118f13f0e422a4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410511"
---
# <a name="importidl"></a>importidl

Вставляет указанный IDL-файла в созданного IDL-файла.

## <a name="syntax"></a>Синтаксис

```cpp
[ importidl(
   idl_file
) ];
```

### <a name="parameters"></a>Параметры

*idl_file*<br/>
Определяет имя IDL-файла, которые необходимо объединить с IDL-файла, создаваемого для вашего приложения.

## <a name="remarks"></a>Примечания

**Importidl** атрибут C++ помещает разделе за пределами блока библиотеки (в *idl_file*) в вашей программе созданного IDL-файла и в разделе библиотеки (в *idl_file*) в библиотеку раздел для вашей программы создается IDL-файла.

Вы можете использовать **importidl**, например, если вы хотите использовать с вашей созданного IDL-файла вручную IDL-файл.

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
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты компилятора](../windows/compiler-attributes.md)<br/>
[Изолированные атрибуты](../windows/stand-alone-attributes.md)<br/>
[import](../windows/import.md)<br/>
[importlib](../windows/importlib.md)<br/>
[include](../windows/include-cpp.md)<br/>
[includelib](../windows/includelib-cpp.md)  