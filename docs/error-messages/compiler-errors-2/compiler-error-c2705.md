---
title: "Ошибка компилятора C2705 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2705"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2705"
ms.assetid: 29249ea3-4ea7-4105-944b-bdb83e8d6852
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C2705
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"метка": недопустимый переход в область видимости "блока обработки исключений"  
  
 При выполнении осуществляется переход к метке, находящейся в одном из блоков `try`\/`catch`, `__try`\/`__except`, `__try`\/`__finally`.  Дополнительные сведения см. в разделе [Обработка исключений](../../cpp/exception-handling-in-visual-cpp.md).  
  
 Следующий пример приводит к возникновению ошибки C2705:  
  
```  
// C2705.cpp  
int main() {  
goto trouble;  
   __try {  
      trouble: ;   // C2705  
   }  
   __finally {}  
  
   // try the following line instead  
   // trouble: ;  
}  
```