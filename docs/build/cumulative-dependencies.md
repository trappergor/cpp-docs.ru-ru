---
title: "Кумулятивные зависимости | Microsoft Docs"
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
  - "зависимости, накопительное"
  - "кумулятивные зависимости (NMAKE)"
  - "зависимости"
ms.assetid: fa6dd777-80b8-437d-87a7-aec0ed818a49
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Кумулятивные зависимости
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Зависимости являются кумулятивными в блоке описания, если целевой объект повторяется.  
  
 Например это набор правил,  
  
```Output  
bounce.exe : jump.obj  
bounce.exe : up.obj  
   echo Building bounce.exe...  
```  
  
 оценивается как это:  
  
```Output  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
```  
  
 Несколько целевых объектов в нескольких строках зависимостей одного блока описания оцениваются, как если бы каждый объект был указан в отдельном блоке описания, но целевые объекты, которые не находятся в последней строке зависимости следует использовать блок команд. NMAKE предпринимает попытку использовать правило определения для таких целей.  
  
 Например это набор правил,  
  
```Output  
leap.exe bounce.exe : jump.obj  
bounce.exe climb.exe : up.obj  
   echo Building bounce.exe...  
```  
  
 оценивается как это:  
  
```Output  
  
leap.exe : jump.obj  
# invokes an inference rule  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
climb.exe : up.obj  
   echo Building bounce.exe...  
```  
  
## <a name="see-also"></a>См. также раздел  
 [Целевые объекты](../build/targets.md)