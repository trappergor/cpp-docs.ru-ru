---
title: "Побочные эффекты зависимостей | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Побочные эффекты зависимостей"
  - "Программа NMAKE, зависимые элементы"
ms.assetid: d4e8db25-fdc0-4d73-81ec-1538f2e1b3e8
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Побочные эффекты зависимостей
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Если целевой объект указан с двоеточия (:) в двух строках зависимостей в разных местах и команды появляться только в одной из строк, NMAKE интерпретирует зависимости, как если бы смежные или объединить. Он не вызывается правило зависимости для зависимости, команды не, но вместо этого предполагается, что зависимости относятся к одному блоку описания и выполняет команды, указанные для другой зависимости. Например это набор правил:  
  
```Output  
bounce.exe : jump.obj  
   echo Building bounce.exe...  
  
bounce.exe : up.obj  
```  
  
 оценивается как это:  
  
```Output  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
```  
  
 Этот эффект не возникает при использовании двойных кавычек (`::`) используется. Например это набор правил:  
  
```Output  
bounce.exe :: jump.obj  
   echo Building bounce.exe...  
  
bounce.exe :: up.obj  
```  
  
 оценивается как это:  
  
```Output  
bounce.exe : jump.obj  
   echo Building bounce.exe...  
  
bounce.exe : up.obj  
# invokes an inference rule  
```  
  
## <a name="see-also"></a>См. также  
 [Целевые объекты](../build/targets.md)