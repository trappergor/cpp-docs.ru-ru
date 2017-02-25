---
title: "Ошибка компилятора C2733 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2733"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2733"
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка компилятора C2733
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

вторая С\-компоновка перегруженной функции "функция" не допускается  
  
 Посредством С\-компоновки объявлено несколько перегруженных функций.  При использовании С\-компоновки только одна форма указанной функции может быть внешней.  Поскольку перегруженные функции имеют то же недекорированное имя, они не могут использоваться для программ на С.  
  
 Следующий пример приводит к возникновению ошибки C2733:  
  
```  
// C2733.cpp  
extern "C" {  
   void F1(int);  
}  
  
extern "C" {  
   void F1();   // C2733  
   // try the following line instead  
   // void F2();  
}  
```