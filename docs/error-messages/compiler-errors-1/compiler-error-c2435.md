---
title: "Ошибка компилятора C2435 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2435"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2435"
ms.assetid: be6aa8f8-579b-42ea-bdd8-2d01393646ad
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Ошибка компилятора C2435
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

var: для динамической инициализации требуется управляемый CRT; невозможна компиляция с параметром \/clr:safe  
  
 Инициализация глобальных локальных переменных для каждого приложения библиотеки CRT, скомпилированной при помощи`/clr:pure`, не создает образов с возможностью проверки.  
  
 Дополнительные сведения см. в разделах [домен приложения](../Topic/appdomain.md) и [процесс](../../cpp/process.md).  
  
 Следующий пример приводит к возникновению ошибки C2435:  
  
```  
// C2435.cpp  
// compile with: /clr:safe /c  
int globalvar = 0;   // C2435  
  
__declspec(process)  
int globalvar2 = 0;  
```