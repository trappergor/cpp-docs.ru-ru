---
title: "Предупреждение компилятора (уровень 4) C4289 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4289"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4289"
ms.assetid: 0dbd2863-4cde-4e16-894b-104a2d5fa724
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Предупреждение компилятора (уровень 4) C4289
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

использовано нестандартное расширение : "переменная" : переменная управления циклом, объявленная в цикле for, используется вне области видимости этого цикла  
  
 При компиляции с параметрами [\/Ze](../../build/reference/za-ze-disable-language-extensions.md) и **\/Zc:forScope\-** объявленная в цикле [for](../../cpp/for-statement-cpp.md) переменная была использована вне области видимости цикла **for**.  
  
 Дополнительные сведения о способах указания стандартного поведения в циклах **for** с помощью параметра **\/Ze** см. в разделе, посвященном параметру [\/Zc:forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md).  
  
 Данное предупреждение по умолчанию отключено.  Дополнительные сведения см. в разделе [Отключенные по умолчанию предупреждения компилятора](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md).  
  
 Следующий пример приводит к возникновению ошибки C4289:  
  
```  
// C4289.cpp  
// compile with: /W4 /Zc:forScope-  
#pragma warning(default:4289)  
int main() {  
   for (int i = 0 ; ; )   // C4289  
      break;  
   i++;  
}  
```