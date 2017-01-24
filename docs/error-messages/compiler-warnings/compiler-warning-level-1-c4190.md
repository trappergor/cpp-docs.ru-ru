---
title: "Предупреждение компилятора (уровень 1) C4190 | Microsoft Docs"
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
  - "C4190"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4190"
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4190
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

для "идентификатор1" задана компоновка в стиле Си, но возвращаемый тип UDT "идентификатор2" несовместим с языком Си  
  
 Функция или указатель функции имеет возвращаемый тип UDT \(тип, определяемый пользователем, который является классом, структурой, перечислением, объединением или значением [\_\_value](../../misc/value.md)\) и компоновку С `extern`.  Это допустимо в следующих случаях.  
  
-   Все вызовы этой функции происходят из C\+\+.  
  
-   Определение этой функции находится в C\+\+.  
  
## Пример  
  
```  
// C4190.cpp  
// compile with: /W1 /LD  
struct X  
{  
   int i;  
   X ();  
   virtual ~X ();  
};  
  
extern "C" X func ();   // C4190  
```