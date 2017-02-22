---
title: "Ошибка компилятора C2690 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2690"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2690"
ms.assetid: f165a806-14bd-4942-99b7-8a9fc7dea227
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# Ошибка компилятора C2690
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

operator: невозможно выполнять расчеты с указателями для управляемого массива или массива WinRT  
  
 Расчеты с указателями не поддерживаются для управляемого массива или массива WinRT.  Используйте нотацию индекса массива для обхода массива.  
  
 **Управляемые расширения для C\+\+**  
  
 Расчеты с указателями не поддерживаются для массива [\_\_gc](../Topic/__gc.md).  Используйте нотацию индекса массива для обхода массива.  
  
 Следующий пример приводит к возникновению ошибки C2690:  
  
```  
// C2690b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
int main() {  
   String* x[] = new String*[10];  
   x[0] = "test";  
   Console::WriteLine(x[0]);  
   x++;   // C2690  
}  
```