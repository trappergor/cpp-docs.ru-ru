---
title: "tlbid | Microsoft Docs"
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
  - "tlbid"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "tlbid - атрибут"
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# tlbid
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к языку C\+\+**  
  
 Позволяет загружать библиотеки, отличные от основной библиотеки типов.  
  
## Синтаксис  
  
```  
tlbid(number)  
```  
  
#### Параметры  
 `number`  
 Номер библиотеки типов в файле с именем `filename`.  
  
## Заметки  
 Если в одну библиотеку DLL встроено несколько библиотек типов, с помощью `tlbid` можно загружать библиотеки, отличные от основной библиотеки типов.  
  
 Например:  
  
```  
#import <MyResource.dll> tlbid(2)  
```  
  
 эквивалентно выражению:  
  
```  
LoadTypeLib("MyResource.dll\\2");  
```  
  
 **Завершение блока, относящегося только к языку C\+\+**  
  
## См. также  
 [Атрибуты \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [Директива \#import](../Topic/%23import%20Directive%20\(C++\).md)