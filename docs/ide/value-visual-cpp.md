---
title: "&lt;value&gt; (Visual C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "value"
  - "<value>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<value> - XML-тег C++"
  - "value - XML-тег C++"
ms.assetid: 0ba0a0d5-bcd7-4862-a169-83f2721ad80e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;value&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Тег \<value\> позволяет описать свойства и методы доступа к свойству.  Обратите внимание, что при добавлении свойства с помощью кода в интегрированной среде разработки Visual Studio, она добавляет тег [\<summary\>](../ide/summary-visual-cpp.md) для нового свойства.  Затем следует вручную добавить тег \<value\>, предназначенный для описания представляемого этим свойством значения.  
  
## Синтаксис  
  
```  
<value>property-description</value>  
```  
  
#### Параметры  
 `property-description`  
 Описание свойства.  
  
## Заметки  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md).  
  
## Пример  
  
```  
// xml_value_tag.cpp  
// compile with: /LD /clr /doc  
// post-build command: xdcmake xml_value_tag.dll  
using namespace System;  
/// Text for class Employee.  
public ref class Employee {  
private:  
   String ^ name;  
   /// <value>Name accesses the value of the name data member</value>  
public:  
   property String ^ Name {  
      String ^ get() {  
         return name;   
      }  
      void set(String ^ i) {  
         name = i;  
      }  
   }  
};  
```  
  
## См. также  
 [Документация XML](../ide/xml-documentation-visual-cpp.md)