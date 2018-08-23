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
ms.openlocfilehash: 9bb6c1bd23eaf705f6ceb57e5fc4ea3354c0ddfc
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42571362"
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

*idl_file*  
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

[Атрибуты компилятора](../windows/compiler-attributes.md)  
[Изолированные атрибуты](../windows/stand-alone-attributes.md)  
[import](../windows/import.md)  
[importlib](../windows/importlib.md)  
[include](../windows/include-cpp.md)  
[includelib](../windows/includelib-cpp.md)  