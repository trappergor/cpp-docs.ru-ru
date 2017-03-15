---
title: "Предупреждение компилятора (уровень 1) C4526 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4526"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4526"
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Предупреждение компилятора (уровень 1) C4526
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция": статическая функция\-член не может переопределить виртуальную функцию, переопределение "виртуальной функции" пропускается, виртуальная функция будет скрыта  
  
 Статическая функция\-член удовлетворяет критериям для переопределения виртуальной функции, вследствие чего функция\-член является одновременно виртуальной и статической.  
  
 Следующий код вызывает ошибку C4526:  
  
```  
// C4526.cpp  
// compile with: /W1 /c  
// C4526 expected  
struct myStruct1 {  
   virtual void __stdcall func( int ) = 0;  
};  
  
struct myStruct2: public myStruct1 {  
   static void __stdcall func( int );  
};  
```  
  
 Возможны следующие варианты устранения проблемы:  
  
-   Если функция должна переопределить виртуальную функцию базового класса, следует удалить статический спецификатор.  
  
-   Если функция должна являться статической функцией\-членом, необходимо переименовать ее, чтобы не возникло конфликта этой функции с виртуальной функцией базового класса.