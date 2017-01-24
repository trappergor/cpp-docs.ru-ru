---
title: "Ошибка компилятора C2884 | Microsoft Docs"
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
  - "C2884"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2884"
ms.assetid: 8b4d43e3-3fb5-4360-86c8-de59d8736d4f
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2884
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"имя": присутствует в объявлении использования, вступает в конфликт с объявлением функции "функция"  
  
 Попытка многократного определения функции.  Первое определение является локальным.  Второе определение содержится в пространстве имен, объявленном с помощью ключевого слова `using`.  
  
 Следующий пример приводит к возникновению ошибки C2884:  
  
```  
// C2884.cpp  
namespace A {  
   void z(int);  
}  
  
void f() {  
   void z(int);  
   using A::z;   // C2884 z is already defined  
}  
```