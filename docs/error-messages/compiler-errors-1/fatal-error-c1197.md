---
title: "Неустранимая ошибка C1197 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1197"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1197"
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Неустранимая ошибка C1197
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

невозможно сослаться на "mscorlib.dll\_1", поскольку на данную программу уже есть ссылка "mscorlib.dll\_2"  
  
 Компилятор соответствует версии среды CLR.  Однако были предприняты попытки сослаться на версию файла среды CLR из предыдущей версии.  
  
 Чтобы разрешить эту ошибку, ссылайтесь только на файлы из тех версий среды CLR, которые поставляются с той версией Visual C\+\+, с которой выполняется компиляция.  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C1197:  
  
```  
// C1197.cpp  
// compile with: /clr /c  
// processor: x86  
#using "C:\Windows\Microsoft.NET\Framework\v1.1.4322\mscorlib.dll"   // C1197  
// try the following line instead  
// #using "mscorlib.dll"  
```