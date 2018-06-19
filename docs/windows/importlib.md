---
title: importlib | Документы Microsoft
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
ms.openlocfilehash: c21b97e50fa03861245a0c0881963387dd8a3102
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876762"
---
# <a name="importlib"></a>importlib
Делает типы, которые уже были скомпилированы в другую библиотеку типов, доступными для создаваемой библиотеки типов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ importlib(  
   "tlb_file"  
) ];  
```  
  
#### <a name="parameters"></a>Параметры  
 *tlb_file*  
 Заключенное в кавычки имя TLB-файла, который необходимо импортировать в библиотеку типов текущего проекта.  
  
## <a name="remarks"></a>Примечания  
 **Importlib** языка C++ вызывает `importlib` инструкции помещается в блок library созданного IDL-файла. **Importlib** атрибут имеет ту же функциональность, что [importlib](http://msdn.microsoft.com/library/windows/desktop/aa367050) языка MIDL.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример использования **importlib**:  
  
```  
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
 [Импорт](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [Включить](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)