---
title: "Предупреждение компилятора (уровень 1) C4129 | Microsoft Docs"
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
  - "C4129"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4129"
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4129
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"символ": неизвестная escape\-последовательность  
  
 Не удалось распознать символ `character` после обратной косой черты в символьной или строковой константе как допустимую escape\-последовательность.  Обратная косая черта пропускается и не печатается.  Символ, следующий за обратной косой чертой, печатается.  
  
 Чтобы напечатать одну косую обратную черту, необходимо указать двойную обратную черту \(\\\\\).  
  
 Escape\-последовательности рассматриваются в разделе 2.13.2 стандарта C\+\+.  
  
 Следующий пример приводит к возникновению ошибки C4129:  
  
```  
// C4129.cpp  
// compile with: /W1  
int main() {  
   char array1[] = "\/709";   // C4129  
   char array2[] = "\n709";   // OK  
}  
```