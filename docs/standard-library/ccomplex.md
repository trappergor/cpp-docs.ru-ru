---
title: "&lt;ccomplex&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<ccomplex>"
dev_langs: 
  - "C++"
ms.assetid: a9fcb5f0-88e3-464b-a5fd-d1afb8cd7e6f
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# &lt;ccomplex&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Включает заголовок стандартной библиотеки C [\<complex\>](../Topic/%3Ccomplex%3E.md), который включает заголовок \<complex.h\> и добавляет связанные имена в пространство имен `std`.  
  
## Синтаксис  
  
```cpp  
  
#include <ccomplex>  
  
```  
  
## Заметки  
 Включение этого заголовка гарантирует, что имена, объявленные с помощью внешней компоновки в заголовке стандартной библиотеки C, объявляются в пространстве имен `std`.  
  
 Имя `clog`, которое объявлено в \<complex.h\>, не определено в пространстве имен `std` из\-за возможных конфликтов с именем `clog`, объявленным в [\<iostream\>](../standard-library/iostream.md).  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Обзор STL](../standard-library/cpp-standard-library-overview.md)