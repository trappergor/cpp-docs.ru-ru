---
title: "Ошибка вычислителя выражений CXX0024 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CXX0024"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0024"
  - "CXX0024"
ms.assetid: eca6adbd-8ff2-4f51-a1cc-a2e9d5d0a47d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ошибка вычислителя выражений CXX0024
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

операции требуется L\-значение  
  
 Для операции, требующей L\-значение, задано выражение, которое не рассчитывает L\-значение.  
  
 L\-значение \(называемое так, потому что оно располагается в левой части оператора присваивания\) — это выражение, ссылающееся на расположение в памяти.  
  
 Например, выражение `buffer[count]` является допустимым L\-значением, потому что оно указывает на конкретное расположение в памяти.  Логическое сравнение `zed != 0` не является допустимым L\-значением, так как его результатом является значение TRUE или FALSE, а не адрес памяти.  
  
 Эта ошибка идентична ошибке CAN0024.