---
title: "Несколько объектов | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "makefile-файлы, целевые объекты"
  - "несколько целевых объектов (NMAKE)"
  - "целевые объекты, несколько в (NMAKE)"
  - "Программа NMAKE, целевые объекты"
ms.assetid: b609a179-0b9f-4b08-9930-998047588ae0
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Несколько объектов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

NMAKE вычисляет целевые объекты в одиночной зависимости, как если бы каждый объект был указан в отдельном блоке описания.  
  
 Например это...  
  
```Output  
bounce.exe leap.exe : jump.obj  
   echo Building...  
```  
  
 .. вычисляется как это:  
  
```Output  
bounce.exe : jump.obj  
   echo Building...  
leap.exe : jump.obj  
   echo Building...  
```  
  
## <a name="see-also"></a>См. также  
 [Целевые объекты](../build/targets.md)