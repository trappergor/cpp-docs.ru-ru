---
title: "Предупреждение командной строки D9026 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "D9026"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D9026"
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение командной строки D9026
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

параметры применяются ко всей командной строке  
  
 Параметр был указан в командной строке после определения имени файла.  Параметр был применен к файлу, расположенному перед ним.  
  
 Например, в командной строке  
  
```  
CL verdi.c /G5 puccini.c  
```  
  
 файл VERDI.c будет компилироваться с помощью параметра \/G5, а не \/G4 по умолчанию.  
  
 Такое поведение отличается от некоторых предыдущих версий, которые применяли только параметры, указанные перед именем файла, что приводило к тому, что VERDI.c компилировался с помощью \/G4, а PUCCINI.c с помощью \/G5.