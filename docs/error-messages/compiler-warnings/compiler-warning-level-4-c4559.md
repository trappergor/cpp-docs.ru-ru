---
title: "Предупреждение компилятора (уровень 4) C4559 | Microsoft Docs"
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
  - "C4559"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4559"
ms.assetid: ed542f60-454d-45cb-85da-987ede61b1ab
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 4) C4559
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : повторное определение; функции добавлен \_\_declspec \(модификатор\)  
  
 Функция была повторно определена или объявлена, и в новом определении или объявлении добавлен модификатор \_\_**declspec** \(***модификатор***\).  Это предупреждение является информационным.  Чтобы устранить это предупреждение, удалите одно из определений.  
  
 Следующий пример приводит к возникновению ошибки C4559:  
  
```  
// C4559.cpp  
// compile with: /W4 /LD  
void f();  
__declspec(noalias) void f();   // C4559  
```