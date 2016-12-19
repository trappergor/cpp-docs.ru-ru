---
title: "Ошибка компилятора C2786 | Microsoft Docs"
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
  - "C2786"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2786"
ms.assetid: 6676d8c0-86dd-4a39-bdda-b75a35f4d137
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2786
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип": недопустимый операнд для \_\_uuidof  
  
 Оператор [\_\_uuidof](../../cpp/uuidof-operator.md) принимает в качестве операнда пользовательский тип с присоединенным идентификатором GUID или объект такого типа.  Возможные причины:  
  
1.  Аргумент не принадлежит к пользовательскому типу.  
  
2.  Оператору `__uuidof` не удается извлечь идентификатор GUID из аргумента.  
  
 Следующий пример приводит к возникновению ошибки C2786:  
  
```  
// C2786.cpp  
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};  
  
int main() {  
   __uuidof(int);   // C2786  
   __uuidof(int *);   // C2786  
   __uuidof(A **);   // C2786  
  
   // no error  
   __uuidof(A);  
   __uuidof(A *);  
   __uuidof(A &);  
   __uuidof(A[]);  
  
   int i;  
   int *pi;  
   A **ppa;  
  
   __uuidof(i);      // C2786  
   __uuidof(pi);     // C2786  
   __uuidof(ppa);    // C2786  
}  
```