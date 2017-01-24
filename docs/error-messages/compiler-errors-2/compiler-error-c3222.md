---
title: "Ошибка компилятора C3222 | Microsoft Docs"
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
  - "C3222"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3222"
ms.assetid: 5624bde8-2fd0-4b8b-92ce-5dfbaf91cf93
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3222
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"parameter": нельзя объявить аргументы по умолчанию для функций\-членов управляемого типа, типа WinRT или универсальных функций  
  
 Запрещено объявлять параметр метода с аргументом по умолчанию.  Перегруженные формы метода — один из способов решения этой проблемы.  То есть вам нужно определить метод с тем же именем без параметров и затем инициализировать переменную в теле метода.  
  
 Следующий пример приводит к возникновению ошибки C3222:  
  
```  
// C3222_2.cpp  
// compile with: /clr  
public ref class G {  
   void f( int n = 0 );   // C3222  
};  
```  
  
 Следующий пример приводит к возникновению ошибки C3222:  
  
```  
// C3222.cpp  
// compile with: /clr:oldSyntax  
public __gc class G {  
   void f( int n = 0 );   // C3222  
};  
```