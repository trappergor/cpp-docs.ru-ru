---
title: "Ошибка компилятора C3382 | Microsoft Docs"
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
  - "C3382"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3382"
ms.assetid: a7603abd-ac4e-4ae6-a02b-3bdc6d1908a6
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3382
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

sizeof при использовании параметра \/clr:safe не поддерживается  
  
 При выполнении компиляции с параметром **\/clr:safe** выходной файл является проверяемым строго типизированным файлом, и параметр sizeof не поддерживается, так как он возвращает значение типа size\_t, размер которого зависит от операционной системы.  
  
 Дополнительные сведения см. в следующих разделах:  
  
-   [Оператор sizeof](../../cpp/sizeof-operator.md)  
  
-   [\/clr \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Общие вопросы использования Visual C\+\+ для 64\-разрядных систем](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3382:  
  
```  
// C3382.cpp // compile with: /clr:safe int main() { sizeof( char );   // C3382 }  
```