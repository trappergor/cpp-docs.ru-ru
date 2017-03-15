---
title: "Предупреждение компилятора (уровень 4) C4623 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4623"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4623"
ms.assetid: e630d8d0-f6ea-469c-a74f-07b027587225
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Предупреждение компилятора (уровень 4) C4623
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"`derived class`": не удалось создать конструктор по умолчанию, так как конструктор по умолчанию для базового класса недоступен или удален  
  
 Конструктор базового класса недоступен и не был создан для производного класса.  Любая попытка создать объект этого типа в стеке приведет к ошибке компилятора.  
  
 Это предупреждение отключено по умолчанию.  Подробнее: [Выключенные по умолчанию предупреждения компилятора](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C4623.  
  
```  
// C4623.cpp  
// compile with: /W4  
#pragma warning(default : 4623)  
class B {  
   B();  
};  
  
class C {  
public:  
   C();  
};  
  
class D : public B {};   // C4623 - to fix, make B's constructor public  
class E : public C {};   // OK - class C constructor is public  
  
int main() {  
   // D d;  will cause an error  
}  
```