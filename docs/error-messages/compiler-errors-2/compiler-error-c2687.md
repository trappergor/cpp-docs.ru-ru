---
title: "Ошибка компилятора C2687 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2687"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2687"
ms.assetid: 1d24b24a-cd0f-41cc-975c-b08dcfb7f402
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C2687
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"type" : объявление исключения не может быть типа "void" и не может обозначать неполный тип, указатель или ссылку на неполный тип  
  
 Чтобы тип являлся частью объявления исключения, он должен быть определен и не быть "void".  
  
 Следующий пример приводит к возникновению ошибки C2687:  
  
```  
// C2687.cpp  
class C;  
  
int main() {  
   try {}  
   catch (C) {}   // C2687 error  
}  
```  
  
 Возможный способ устранения данной ошибки:  
  
```  
// C2687b.cpp  
// compile with: /EHsc  
class C {};  
  
int main() {  
   try {}  
   catch (C) {}  
}  
```