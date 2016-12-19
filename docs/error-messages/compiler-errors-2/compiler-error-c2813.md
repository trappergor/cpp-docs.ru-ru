---
title: "Ошибка компилятора C2813 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2813"
ms.assetid: 6cf2135f-7b82-42d1-909a-5e864308a09c
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2813
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

директива \#import не поддерживается с параметром \/MP  
  
 Ошибка C2813 выводится в случае, когда в команде компилятора задается параметр компилятора **\/MP**, а также два или более файлов для компиляции, и при этом один или несколько файлов содержат директиву препроцессора [\#import](../Topic/%23import%20Directive%20\(C++\).md). Директива [\#import](../Topic/%23import%20Directive%20\(C++\).md) создает классы C\+\+ на основе типов в указанной библиотеке типов, а затем записывает эти классы в два файла заголовков. Директива [\#import](../Topic/%23import%20Directive%20\(C++\).md) не поддерживается, так как в случае, если несколько блоков компиляции импортируют одну и ту же библиотеку типов, между блоками возникает конфликт при попытке одновременной записи одних и тех же файлов заголовков.  
  
 Эта ошибка компилятора и параметр компилятора **\/MP** появились только в [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)].  
  
## Пример  
 Приведенный ниже пример приводит к возникновению ошибки C2813. Командная строка в комментарии "compile with:" предписывает компилятору использовать параметры компилятора **\/MP** и **\/c** для компиляции нескольких файлов. По крайней мере один из файлов содержит директиву [\#import](../Topic/%23import%20Directive%20\(C++\).md). Один и тот же файл используется дважды для проверки данного примера.  
  
```  
// C2813.cpp // compile with: /MP /c C2813.cpp C2813.cpp #import "C:\windows\system32\stdole2.tlb"   // C2813 int main() { }  
```