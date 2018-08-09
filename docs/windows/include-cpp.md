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
ms.openlocfilehash: c21bb7cf58c3c397237768942d60f79958f3278a
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40013565"
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
  
 **Включают** атрибут C++ имеет ту же функциональность, что [включают](http://msdn.microsoft.com/library/windows/desktop/aa367052) описании атрибута MIDL.  
  
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
 [Импорт](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [includelib](../windows/includelib-cpp.md)   
 [importlib](../windows/importlib.md)   