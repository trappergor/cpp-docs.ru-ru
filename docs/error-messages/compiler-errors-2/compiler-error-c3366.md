---
title: "Ошибка компилятора C3366 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3366"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3366"
ms.assetid: efc55bcf-c16d-43c1-a36f-87a6165fa2a8
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Ошибка компилятора C3366
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

variable: статические элементы данных управляемых типов и типов WinRT должны быть заданы внутри определения класса  
  
 Вы попытались сослаться на статический элемент класса WinRT, .NET или на интерфейс вне определения этого класса или интерфейса.  
  
 Компилятору требуется полное определение класса \(для передачи метаданных после одного прохода\), а статические элементы данных должны инициализироваться внутри класса.  
  
 Так, в следующем примере возникает ошибка C3366 и показано, как ее исправить.  
  
```  
// C3366.cpp  
// compile with: /clr /c  
ref class X {  
   public:  
   static int i;   // initialize i here to avoid C3366  
};  
  
int X::i = 5;      // C3366  
```  
  
 В следующем примере возникает ошибка C3366 и показано, как ее исправить.  
  
```  
// C3366_b.cpp  
// compile with: /clr:oldSyntax /c  
__gc struct X {  
   static int i;   // initialize i here to avoid C3366  
};  
  
int X::i = 5;      // C3366  
```