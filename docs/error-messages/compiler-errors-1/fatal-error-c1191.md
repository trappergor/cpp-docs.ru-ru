---
title: "Неустранимая ошибка C1191 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1191"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1191"
ms.assetid: 2888c6c4-b4e6-449e-8ee0-7917f31086df
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Неустранимая ошибка C1191
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

импорт "библиотеки" возможен только в глобальной области видимости  
  
 В программе, скомпилированной с параметром \/clr, инструкция для импорта библиотеки mscorlib.dll должна находиться в глобальной области видимости, а не в пространстве имен или функции.  
  
 Следующий пример приводит к возникновению ошибки C1191:  
  
```  
// C1191.cpp  
// compile with: /clr  
namespace sample {  
   #using <mscorlib.dll>   // C1191 not at global scope  
}  
```  
  
 Возможный способ устранения данной ошибки:  
  
```  
// C1191b.cpp  
// compile with: /clr /c  
#using <mscorlib.dll>  
namespace sample {}  
```