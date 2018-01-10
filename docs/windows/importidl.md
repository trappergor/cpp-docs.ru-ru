---
title: "importidl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.importidl
dev_langs: C++
helpviewer_keywords: importidl attribute
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cd3fb56898107b1eca7cd30e06d75d253a02655e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="importidl"></a>importidl
Вставляет указанный IDL-файла в сгенерированный IDL-файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ importidl(  
   idl_file  
) ];  
```  
  
#### <a name="parameters"></a>Параметры  
 `idl_file`  
 Определяет имя IDL-файла, которую требуется объединить с IDL-файла, создаваемого для вашего приложения.  
  
## <a name="remarks"></a>Примечания  
 **Importidl** атрибута C++ помещает раздел вне блока библиотеки (в `idl_file`) в вашей программе созданного IDL-файла и в разделе библиотеки (в `idl_file`) в раздел библиотеки программы созданного IDL-файла.  
  
 Вы можете использовать **importidl**, например, если вы хотите использовать вручную IDL-файл с вашего созданного IDL-файла.  
  
## <a name="example"></a>Пример  
  
```  
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
 [Импорт](../windows/import.md)   
 [importlib](../windows/importlib.md)   
 [включить](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)   
