---
title: "Ошибка компилятора C3489 | Microsoft Docs"
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
  - "C3489"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3489"
ms.assetid: 47b58d69-459d-4499-abc7-5f0b9303d773
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3489
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Переменная "var" обязательна, если режимом по умолчанию является передача параметров по значению  
  
 Если вы указываете, что для лямбда\-выражения режимом по умолчанию является передача по значению, то в предложение передачи этого выражения нельзя передать переменную по значению.  
  
### Исправление ошибки  
  
-   Не передавайте переменную в предложение передачи явным образом или  
  
-   не указывайте режим передачи по значению в качестве режима по умолчанию.  
  
-   Укажите в качестве режима по умолчанию режим передачи по ссылке.  
  
-   Передайте переменную в предложение передачи по ссылке. \(Это может изменить поведение лямбда\-выражения.\)  
  
## Пример  
 В следующем примере возникает ошибка C3489, так как переменная `n` передается по значению в предложение передачи лямбда\-выражения, режим передачи по умолчанию которого — по значению:  
  
```  
// C3489a.cpp int main() { int n = 5; [=, n]() { return n; } (); // C3489 }  
```  
  
## Пример  
 В следующем примере показано четыре возможных способа устранения ошибки C3489.  
  
```  
// C3489b.cpp int main() { int n = 5; // Possible resolution 1: // Do not explicitly pass n to the capture clause. [=]() { return n; } (); // Possible resolution 2: // Do not specify by-value as the default capture mode. [n]() { return n; } (); // Possible resolution 3: // Specify by-reference as the default capture mode. [&, n]() { return n; } (); // Possible resolution 4: // Pass n by reference to the capture clause. [&n]() { return n; } (); }  
```  
  
## См. также  
 [Лямбда\-выражения](../../cpp/lambda-expressions-in-cpp.md)