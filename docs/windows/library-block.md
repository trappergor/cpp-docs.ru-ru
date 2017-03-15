---
title: "library_block | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.library_block"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "library_block attribute"
ms.assetid: ae7a7ebe-5e1a-4eda-a058-11bbd058ece8
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# library_block
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Задает конструкцию внутри блока библиотеки IDL.  
  
## Синтаксис  
  
```  
  
[library_block]  
  
```  
  
## Заметки  
 При установке конструкцию внутри блока библиотеки, можно гарантировать, что он будут передаваться в библиотеку типов, независимо от того, является ли она ссылается.  По умолчанию только измененные конструкции [CoClass](../windows/coclass.md)"  [dispinterface](../windows/dispinterface.md)и  [idl\_module](../windows/idl-module.md) атрибуты помещаются в блоке библиотеки.  
  
## Пример  
 В следующем коде пользовательский интерфейс размещается внутри блока библиотеки.  
  
```  
// cpp_attr_ref_library_block.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLib")];  
[object, library_block, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]  
__interface IMyInterface {  
   HRESULT f1();  
};  
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
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Stand\-Alone Attributes](../Topic/Stand-Alone%20Attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)