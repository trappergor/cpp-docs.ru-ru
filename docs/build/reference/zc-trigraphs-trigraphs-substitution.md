---
title: "/Zc:trigraphs (подстановка триграфов) | Microsoft Docs"
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
  - "/Zc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc - параметры компилятора (C++)"
  - "параметры компилятора - совместимость"
  - "Zc - параметры компилятора (C++)"
  - "-Zc - параметры компилятора (C++)"
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zc:trigraphs (подстановка триграфов)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

При указании параметра **\/Zc:trigraphs** компилятор заменяет последовательность символов триграфов, используя соответствующие знаки пунктуации.  Чтобы отключить подстановку триграфов, укажите параметр **\/Zc:trigraphs\-**.  По умолчанию **\/Zc:trigraphs** отключен.  
  
## Синтаксис  
  
```  
/Zc:trigraphs[-]  
```  
  
## Заметки  
 Триграф состоит из двух последовательных вопросительных знаков \("??"\), за которыми следует третий уникальный знак.  Например, компилятор заменяет триграф "??\=" с помощью символа "\#".  Следует использовать триграфы в файлах ресурсов С, которые используют набор символов, не содержащий подходящего графического представления для некоторых знаков пунктуации.  
  
 Список триграфов C\/C\+\+ и пример их использования см. в разделе [Триграфы](../Topic/Trigraphs.md).  
  
## См. также  
 [\/Zc \(соответствие\)](../../build/reference/zc-conformance.md)   
 [Триграфы](../Topic/Trigraphs.md)