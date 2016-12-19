---
title: "import | Microsoft Docs"
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
  - "vc-attr.import"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "import attribute"
ms.assetid: ebf07cae-39fb-4047-8b57-54af0a9a83de
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# import
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет другие idl, .odl или файл заголовка, содержащий определения необходимости ссылаться из основного языка IDL.  
  
## Синтаксис  
  
```  
  
      [ import(  
   idl_file  
) ];  
```  
  
#### Параметры  
 `idl_file`  
 Имя idl\-файла, импортированные в библиотеку типов текущего проекта.  
  
## Заметки  
 **импорт** Приводит к тому, что атрибут C\+\+  `#import` оператор, который необходимо поместить в разделе  `import "docobj.idl"` выписка в созданном файле idl.  **импорт** атрибут имеет ту же функциональность, что и  [импорт](http://msdn.microsoft.com/library/windows/desktop/aa367047) атрибут MIDL.  
  
 **импорт** атрибут только устанавливает указанный файл в idl\-файл, который будет создан проектом;   **импорт** атрибут не позволяет вызывать конструкции в указанном файле от исходного кода в проекте.  Вызов конструирования в указанном файле от исходного кода в проекте, любая использование [\#import](../Topic/%23import%20Directive%20\(C++\).md) и  `embedded_idl` атрибут или можно включать h\-файл,  `idl_file`h\-файл, если существует.  
  
## Пример  
 Следующий код:  
  
```  
// cpp_attr_ref_import.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[import(import.idl)];  
```  
  
 создает следующий код в созданном файле idl.  
  
```  
import "docobj.idl";  
import "import.idl";  
  
[ uuid(EED3644C-8488-3ECD-BA97-147DB3CDB499), version(1.0) ]  
library MyLib {  
   importlib("stdole2.tlb");  
   importlib("olepro32.dll");  
...  
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
 [importidl](../windows/importidl.md)   
 [importlib](../windows/importlib.md)   
 [include](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)