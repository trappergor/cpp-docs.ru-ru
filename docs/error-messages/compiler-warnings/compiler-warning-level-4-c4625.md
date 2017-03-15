---
title: "Предупреждение компилятора (уровень 4) C4625 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4625"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4625"
ms.assetid: 4cc99e50-846c-4784-97da-48b977067851
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Предупреждение компилятора (уровень 4) C4625
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"производный класс": не удалось создать конструктор копии, так как конструктор копии для базового класса недоступен или удален  
  
 Конструктор копирования был удален или недоступен для базового класса, поэтому он не был создан для производного класса.  Любая попытка создать объект этого типа приведет к ошибке компилятора.  
  
 Это предупреждение отключено по умолчанию.  Подробнее: [Выключенные по умолчанию предупреждения компилятора](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md).  
  
## Пример  
 В следующем примере показано возникновение ошибки C4625 и приводятся сведения по ее устранению.  
  
```  
// C4625.cpp  
// compile with: /W4 /c  
#pragma warning(default : 4625)  
  
struct A {  
   A() {}  
  
private:  
   A(const A&) {}  
};  
  
struct C : private virtual A {};  
struct B :  C {};   // C4625 no copy constructor  
  
struct D : A {};  
struct E :  D {};   // OK  
```