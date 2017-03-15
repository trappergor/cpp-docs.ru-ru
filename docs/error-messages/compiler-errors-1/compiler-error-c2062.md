---
title: "Ошибка компилятора C2062 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2062"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2062"
ms.assetid: 6cc98353-2ddf-43ab-88a2-9cc91cdd6033
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C2062
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

непредвиденный тип "тип"  
  
 Компилятор не предвидел имени типа.  
  
 Следующий пример приводит к возникновению ошибки C2062:  
  
```  
// C2062.cpp  
// compile with: /c  
struct A {  : int l; };   // C2062  
struct B { private: int l; };   // OK  
```  
  
 Ошибка C2062 также может возникать из\-за способа обработки компилятором неопределенных типов в списке параметров конструктора.  Если компилятор обнаруживает неопределенный тип \(с ошибкой в имени?\), он предполагает, что конструктор является выражением, и создает ошибку C2062.  Для ее исправления следует использовать в списке параметров конструктора только определенные типы.