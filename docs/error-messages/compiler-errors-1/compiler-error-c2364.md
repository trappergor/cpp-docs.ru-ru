---
title: "Ошибка компилятора C2364 | Microsoft Docs"
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
  - "C2364"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2364"
ms.assetid: 4f550571-94b5-42ca-84cb-663fecbead44
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2364
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип": недопустимый тип для пользовательского атрибута  
  
 Именованные аргументы для пользовательских атрибутов ограничены константными выражениями времени компиляции.  Например, целочисленные типы \(int, char и т. д.\), System::Type^, и System::Object^.  
  
## Пример  
 Следующий пример демонстрирует причины возникновения ошибки C2364.  
  
```  
// c2364.cpp  
// compile with: /clr /c  
using namespace System;  
  
[attribute(AttributeTargets::All)]  
public ref struct ABC {  
public:  
   // Delete the following line to resolve.  
   ABC( Enum^ ) {}   // C2364  
   ABC( int ) {}   // OK  
};  
```