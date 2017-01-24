---
title: "Ошибка компилятора C3887 | Microsoft Docs"
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
  - "C3887"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3887"
ms.assetid: a7e82426-ef99-437b-9562-2822004e18fe
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3887
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"var": инициализатором элемента данных\-литерала должно быть выражение константы  
  
 Инициализация элемента данных\-[литерала](../../windows/literal-cpp-component-extensions.md) может производиться только с помощью выражения константы.  
  
 Следующий пример приводит к возникновению ошибки C3887:  
  
```  
// C3887.cpp  
// compile with: /clr  
ref struct Y1 {  
   static int i = 9;  
   literal  
   int staticConst = i;   // C3887  
};  
```  
  
 Возможный способ устранения данной ошибки:  
  
```  
// C3887b.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   literal  
   int staticConst = 9;  
};  
```