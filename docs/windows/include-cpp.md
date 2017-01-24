---
title: "include (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.include"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "include attribute"
ms.assetid: d23f8b91-fe5b-48fa-9371-8bd73af7b8e3
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# include (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указывает один или более файлов заголовков, которые нужно включить в созданном файле idl.  
  
## Синтаксис  
  
```  
  
      [ include(  
   header_file  
) ];  
```  
  
#### Параметры  
 *header\_file*  
 Имя файла, для которого требуется включенный в созданном файле idl.  
  
## Заметки  
 **include** Приводит к тому, что атрибут C\+\+  `#include` оператор, который необходимо поместить в разделе  `import "docobj.idl"` выписка в созданном файле idl.  
  
 **include** Атрибут C\+\+ имеет ту же функциональность, что и  [include](http://msdn.microsoft.com/library/windows/desktop/aa367052) атрибут MIDL.  
  
## Пример  
 Следующий код демонстрирует пример использования include.  В данном примере файл include.h содержит только выписку \#include.  
  
```  
// cpp_attr_ref_include.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[include(cpp_attr_ref_include.h)];  
```  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Любой|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|None|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../Topic/Stand-Alone%20Attributes.md)   
 [import](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [includelib](../windows/includelib-cpp.md)   
 [importlib](../windows/importlib.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)