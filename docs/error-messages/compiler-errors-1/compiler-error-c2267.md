---
title: "Ошибка компилятора C2267 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2267"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2267"
ms.assetid: ea63bebb-6208-4367-8440-39be07f9c360
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C2267
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : статические функции с блоковой областью действия недопустимы  
  
 Локальная функция объявлена как `static`.  У статических функций область действия должна быть глобальной.  
  
 Следующий пример приводит к возникновению ошибки C2267:  
  
```  
// C2267.cpp  
static int func2();   // OK  
int main() {  
    static int func1();   // C2267  
}  
```