---
title: "Предупреждение компилятора C4959 | Microsoft Docs"
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
  - "C4959"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4959"
ms.assetid: 3a128f3e-4d8a-4565-ba1a-5d32fdeb5982
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора C4959
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

не удается определить неуправляемую структуру "тип" в \/clr:safe, поскольку доступ к ее членам выдает код, недоступный для проверки  
  
 Обращение к члену неуправляемого типа приводит к формированию непроверяемого \(peverify.exe\) образа.  
  
 Для получения дополнительной информации см. [Чистый и проверяемый код](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Это предупреждение выдается в качестве ошибки, и его можно отключить с помощью директивы pragma [warning](../../preprocessor/warning.md) или параметра компилятора [\/wd](../../build/reference/compiler-option-warning-level.md).  
  
 Следующий пример приводит к возникновению предупреждения C4959:  
  
```  
// C4959.cpp // compile with: /clr:safe // Uncomment the following line to resolve. // #pragma warning( disable : 4959 ) struct X { int data; }; int main() { X x; x.data = 10;   // C4959 }  
```