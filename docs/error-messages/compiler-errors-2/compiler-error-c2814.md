---
title: "Ошибка компилятора C2814 | Microsoft Docs"
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
  - "C2814"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2814"
ms.assetid: 7d165136-a08b-4497-a76d-60a21bb19404
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2814
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

member: неуправляемый тип не может быть вложенным в управляемом типе или типе WinRT "type"  
  
## Пример  
 Неуправляемый тип не может быть вложенным в типе CLR или WinRT.  В следующем примере показано возникновение ошибки C2814 и приводятся сведения по ее устранению.  
  
```  
// C2814.cpp  
// compile with: /clr /c  
ref class A {  
   class B {};   // C2814  
   ref class C {};   // OK  
};  
```  
  
## Пример  
 С помощью управляемых расширений для C\+\+ необходимо явно указать "управляемость" встроенного типа, используя одно из следующих ключевых слов: [\_\_gc](../Topic/__gc.md), [\_\_nogc](../../misc/nogc.md) или [\_\_value](../../misc/value.md).  
  
 В следующем примере показано возникновение ошибки C2814 и приводятся сведения по ее устранению.  
  
```  
// C2814_b.cpp  
// compile with: /clr:oldSyntax /c  
__gc class A {  
   class B {};   // C2814  
   __gc class C {};   // OK  
};  
```