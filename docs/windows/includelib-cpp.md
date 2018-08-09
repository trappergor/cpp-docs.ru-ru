---
title: includelib (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.includelib
dev_langs:
- C++
helpviewer_keywords:
- includelib attribute
ms.assetid: cd90ea6e-5ae8-4f11-b8d1-662db95412b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3d6f6a4dc4f23460b3661da4ed3775708cac9b6d
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40016181"
---
# <a name="includelib-c"></a>includelib (C++)
В результате файл IDL или .h, должны быть включены в созданного IDL-файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
[ includelib(  
   name.idl  
) ];  
```  
  
### <a name="parameters"></a>Параметры  
 *Name.IDL*  
 Имя IDL-файла, который будет частью созданного IDL-файла.  
  
## <a name="remarks"></a>Примечания  
 **Includelib** атрибут C++ вызывает файл IDL или .h, должны быть включены в созданного IDL-файла, после `importlib` инструкции.  
  
## <a name="example"></a>Пример  
 В CPP-файле отображается следующий код:  
  
```cpp  
// cpp_attr_ref_includelib.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[includelib("includelib.idl")];  
```  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|В любом месте|  
|**Повторяемый**|Да|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Изолированные атрибуты](../windows/stand-alone-attributes.md)   
 [Импорт](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [включить](../windows/include-cpp.md)   
 [importlib](../windows/importlib.md)   