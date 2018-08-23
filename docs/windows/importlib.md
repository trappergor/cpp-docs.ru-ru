---
title: importlib | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.importlib
dev_langs:
- C++
helpviewer_keywords:
- importlib attribute
ms.assetid: f129e459-b8d3-4aca-a0bc-ee53e18b62ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b9522db579641d79b8b77cc870cd1df6f03c0413
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42607677"
---
# <a name="importlib"></a>importlib

Делает типы, которые уже были скомпилированы в другую библиотеку типов, доступными для создаваемой библиотеки типов.

## <a name="syntax"></a>Синтаксис

```cpp
[ importlib(
   "tlb_file"
) ];
```

### <a name="parameters"></a>Параметры

*tlb_file*  
Заключенное в кавычки имя TLB-файла, который необходимо импортировать в библиотеку типов текущего проекта.

## <a name="remarks"></a>Примечания

**Importlib** C++ атрибут приводит к `importlib` инструкцию, чтобы поместить в блок library созданного IDL-файла. **Importlib** атрибут имеет ту же функциональность, что [importlib](http://msdn.microsoft.com/library/windows/desktop/aa367050) описании атрибута MIDL.

## <a name="example"></a>Пример

Ниже показан пример использования **importlib**:

```cpp
// cpp_attr_ref_importlib.cpp
// compile with: /LD
[module(name="MyLib")];
[importlib("importlib.tlb")];
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
[importidl](../windows/importidl.md)  
[include](../windows/include-cpp.md)  
[includelib](../windows/includelib-cpp.md)