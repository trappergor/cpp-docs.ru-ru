---
title: "Ошибка компилятора C2071 | Microsoft Docs"
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
  - "C2071"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2071"
ms.assetid: f8c09255-a5c4-47e3-8089-3d875ae43cc5
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2071
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'идентификатор' : недопустимый класс хранилища  
  
 `identifier` был объявлен с недопустимым [класс хранилища](../../c-language/c-storage-classes.md).  Эта ошибка может возникнуть, когда для идентификатора указано несколько классов хранилища или когда определение несовместимо с объявлением класса хранилища.  
  
 Чтобы устранить эту проблему, узнайте нужный класс хранилища для идентификатора, например, `static` или  `extern`, и соответствующим образом исправьте его объявление.  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C2071.  
  
```  
// C2071.cpp  
// compile with: /c  
struct C {  
   extern int i;   // C2071  
};  
struct D {  
   int i;   // OK, no extern on an automatic  
};  
```  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C2071.  
  
```  
// C2071_b.cpp  
// compile with: /c  
typedef int x(int i) { return i; }   // C2071  
typedef int (x)(int);   // OK, no local definition in typedef  
```