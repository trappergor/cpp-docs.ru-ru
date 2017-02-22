---
title: "Ошибка компилятора C2299 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2299"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2299"
ms.assetid: d001c2bc-f6fd-47aa-8e42-0eb824d6441d
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# Ошибка компилятора C2299
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция": изменение поведения. Явная специализация не может быть конструктором копии или оператором назначения копии  
  
 Это ошибка может также возникать в результате действий по обеспечению совместимости компилятора с Visual C\+\+ 2005: предыдущие версии Visual C\+\+ допускали явную специализацию для конструктора копий или оператора назначения копий.  
  
 Для устранения ошибки C2299 используйте конструктор копий или оператор назначения не в качестве функции шаблона, а в качестве нешаблонной функции, которая принимает тип класса.  В любом коде, который вызывает конструктора копий или оператора назначений путем явного указания аргументов шаблона, необходимо удалить аргументы шаблона.  
  
 Следующий пример приводит к возникновению ошибки C2299:  
  
```  
// C2299.cpp  
// compile with: /c  
class C {  
   template <class T>  
   C (T t);  
  
   template <> C (const C&);   // C2299  
   C (const C&);   // OK  
};  
```