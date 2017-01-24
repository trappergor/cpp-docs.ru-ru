---
title: "Предупреждение компилятора (уровень 3) C4414 | Microsoft Docs"
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
  - "C4414"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4414"
ms.assetid: bc81d3ad-55dc-4a6b-a6f2-ec0ef38347df
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 3) C4414
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

функция: короткий переход к функции преобразован в ближний переход  
  
 Сокращенный переход генерирует компактную инструкцию, которая разветвляется на адреса в ограниченном диапазоне из инструкции.  Инструкция включает короткое смещение, которое представляет дистанцию между переходом и конечным адресом, определением функции.  В процессе компоновки функция, возможно, будет перемещена или подвергнута оптимизациям времени выполнения, которые вызывают выход функции из диапазона, доступного из короткого смещения.  Компилятор должен генерировать конкретную запись для перехода, который требует, чтобы инструкция jmp была либо NEAR, либо FAR.  Компилятор сделал преобразование.  
  
 Например, в следующем коде формируется сообщение об ошибке C4414:  
  
```  
// C4414.cpp  
// compile with: /W3 /c  
// processor: x86  
int DoParityEven();  
int DoParityOdd();  
unsigned char global;  
int __declspec(naked) DoParityEither()  
{  
   __asm  
   {  
      test global,0  
      jpe SHORT DoParityEven  // C4414  
      jmp SHORT DoParityOdd   // C4414  
   }  
}  
```