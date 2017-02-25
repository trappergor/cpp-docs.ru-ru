---
title: "Ошибка компилятора C3622 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3622"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3622"
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Ошибка компилятора C3622
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"класс" : нельзя создать экземпляр класса, объявленного как "keyword"  
  
 Предпринята попытка создать экземпляр класса, помеченного как [abstract](../../windows/abstract-cpp-component-extensions.md) \(или [\_\_abstract](../../misc/abstract.md)\).  Класс, помеченный как абстрактный, может использоваться в качестве базового, но создавать экземпляры такого класса нельзя.  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3622.  
  
```  
// C3622.cpp  
// compile with: /clr  
ref class a abstract {};  
  
int main() {  
   a aa;   // C3622  
}  
```  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3622.  
  
```  
// C3622_b.cpp  
// compile with: /clr:oldSyntax  
__abstract class a {  
};  
int main() {  
   a aa;   // C3622  
}  
```