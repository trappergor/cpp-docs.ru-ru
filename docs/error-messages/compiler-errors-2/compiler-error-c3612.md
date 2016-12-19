---
title: "Ошибка компилятора C3612 | Microsoft Docs"
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
  - "C3612"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3612"
ms.assetid: aa6e3a2b-4afa-481c-98c1-1b6d1f82f869
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3612
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип": запечатанный класс не может быть абстрактным  
  
 Типы, определенные с помощью `value` \(или [\_\_value](../../misc/value.md)\) являются по умолчанию запечатанными, а класс является абстрактным, если только он не реализует все методы базового класса.  Запечатанный абстрактный класс не может являться базовым классом, и его экземпляры создаваться не могут.  
  
 Для получения дополнительной информации см. [Классы и структуры](../../windows/classes-and-structs-cpp-component-extensions.md).  
  
 Следующий пример приводит к возникновению ошибки C3612:  
  
```  
// C3612.cpp  
// compile with: /clr /c  
value struct V: public System::ICloneable {};   // C3612  
  
// OK  
value struct V2: public System::ICloneable {  
   Object^ Clone();  
};  
```