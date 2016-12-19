---
title: "Предупреждение компилятора (уровень 1) C4312 | Microsoft Docs"
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
  - "C4312"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4312"
ms.assetid: 541906ed-4f62-4bcb-947f-cf9ae7411bcb
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4312
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"операция": преобразование из "тип 1" в "тип 2" большего размера  
  
 Это предупреждение сообщает о попытке присвоить 32\-разрядное значение 64\-разрядному указателю, например при приведении 32\-разрядного `int` или `long` к 64\-разрядному указателю.  
  
 Это преобразование может быть небезопасным даже для значений указателей, которые помещаются в 32 бита, при расширении знака.  Если отрицательное целое 32\-разрядное число присваивается 64\-разрядному указателю, расширение знака приводит к тому, что значение указателя ссылается на адрес в памяти, отличный от значения целого числа.  
  
 Это предупреждение возникает только для 64\-разрядных целевых сред компиляции.  Подробнее: [Правила использования указателей](http://msdn.microsoft.com/library/windows/desktop/aa384242).  
  
 В следующем примере кода возникает ошибка C4312 при компиляции для 64\-разрядных сред.  
  
```  
// C4312.cpp  
// compile by using: cl /W1 /LD C4312.cpp  
void* f(int i) {  
   return (void*)i;   // C4312 for 64-bit targets  
}  
  
void* f2(__int64 i) {  
   return (void*)i;   // OK  
}  
```