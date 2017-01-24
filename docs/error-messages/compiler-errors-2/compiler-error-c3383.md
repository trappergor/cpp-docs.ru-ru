---
title: "Ошибка компилятора C3383 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3383"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3383"
ms.assetid: ceb7f725-f417-4dc3-8496-0f413bb76687
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3383
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

operator new при использовании параметра \/clr:safe не поддерживается  
  
 Строгая типизация в выходном файле, полученном при компиляции с параметром **\/clr:safe**, поддается проверке, поэтому указатели не поддерживаются.  
  
 Дополнительные сведения см. в следующих разделах:  
  
-   [\/clr \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Общие вопросы использования Visual C\+\+ для 64\-разрядных систем](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3383:  
  
```  
// C3383.cpp // compile with: /clr:safe int main() { char* pCharArray = new char[256];  // C3383 }  
```