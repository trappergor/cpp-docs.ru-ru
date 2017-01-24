---
title: "Предупреждение компилятора (уровень 1) C4091 | Microsoft Docs"
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
  - "C4091"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4091"
ms.assetid: 3a404967-ab42-49b0-b324-fd7ba1859d78
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4091
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"ключевое слово" : игнорируется слева от "типа", если не объявляется переменная  
  
 Компилятор обнаружил ситуацию, где пользователь, вероятно, собирался объявить переменную, но компилятор не смог выполнить это объявление.  
  
## Пример  
 Атрибут `__declspec` в начале объявления пользовательского типа относится к переменным этого типа.  Предупреждение C4091 указывает на то, что объявленных переменных нет.  Следующий пример приводит к возникновению предупреждения C4091.  
  
```  
// C4091.cpp  
// compile with: /W1 /c  
__declspec(dllimport) class X {}; // C4091  
  
// __declspec attribute applies to varX  
__declspec(dllimport) class X2 {} varX;  
  
// __declspec attribute after the class or struct keyword   
// applies to user defined type  
class __declspec(dllimport) X3 {};  
```  
  
## Пример  
 Если идентификатор объявлен как typedef, то он не может также использоваться в качестве имени переменной.  Следующий пример приводит к возникновению предупреждения C4091.  
  
```  
// C4091_b.cpp  
// compile with: /c /W1 /WX  
#define LIST 4  
typedef struct _LIST {} LIST;   // C4091  
```