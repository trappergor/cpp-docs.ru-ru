---
title: "Предупреждение компилятора (уровень 4) C4702 | Microsoft Docs"
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
  - "C4702"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4702"
ms.assetid: d8198c1e-8762-42a6-9e6b-cb568b7a1686
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 4) C4702
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Недостижимый код  
  
 Это предупреждение является результатом работы согласованности компилятора, выполненной для Visual Studio .NET 2003: недостижимый код.  Когда компилятор \(серверный\) обнаруживает недостижимый код, он выдает предупреждение C4702 \(уровень 4\).  
  
 Для кода, действительного как Visual Studio .NET 2003, так и для версий Visual C\+\+ для Visual Studio .NET, удалите недостижимый код или обеспечьте достижимость всего кода для определенного потока выполнения.  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C4702.  
  
```  
// C4702.cpp  
// compile with: /W4  
#include <stdio.h>  
  
int main() {  
   return 1;  
   printf_s("I won't print.\n");   // C4702 unreachable  
}  
```  
  
## Пример  
 При компилировании с **\/GX**, **\/EHc**, **\/EHsc** или  **\/EHac** при использовании внешних функций языка C код может оказаться недостижимым из\-за того, что внешние функции языка C считаются недоступными, и поэтому блок catch недостижим.  Если вам кажется, что предупреждение недействительно по причине доступности функции, компилируйте с **\/EHa** or **\/EHs**, в зависимости от конкретного исключения.  
  
 Дополнительные сведения см. в разделе [Параметр \/EH \(модель обработки исключений\)](../../build/reference/eh-exception-handling-model.md).  
  
 Следующий пример приводит к возникновению ошибки C4702.  
  
```  
// C4702b.cpp  
// compile with: /W4 /EHsc  
#include <iostream>  
  
using namespace std;  
extern "C" __declspec(dllexport) void Function2(){}  
  
int main() {  
   try {  
      Function2();  
   }  
   catch (...) {  
      cout << "Exp: Function2!" << endl;   // C4702  
   }  
}  
```