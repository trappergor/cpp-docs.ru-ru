---
title: Включить (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.include
dev_langs:
- C++
helpviewer_keywords:
- include attribute
ms.assetid: d23f8b91-fe5b-48fa-9371-8bd73af7b8e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 232dfb803e9327b857d26a4294786c2742a1143c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215972"
---
# <a name="include-c"></a>include (C++)

Указывает один или несколько файлов заголовка для включения в созданного IDL-файла.

## <a name="syntax"></a>Синтаксис

```cpp
[ include(
   header_file
) ];
```

### <a name="parameters"></a>Параметры

*HEADER_FILE*  
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

Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)  
[Изолированные атрибуты](../windows/stand-alone-attributes.md)  
[import](../windows/import.md)  
[importidl](../windows/importidl.md)  
[includelib](../windows/includelib-cpp.md)  
[importlib](../windows/importlib.md)  