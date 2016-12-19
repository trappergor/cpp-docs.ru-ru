---
title: "Ошибка компилятора C2594 | Microsoft Docs"
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
  - "C2594"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2594"
ms.assetid: 68cd708f-266e-44b0-a211-3e3ab63b11bf
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2594
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"оператор": неоднозначные преобразования "типа 1" в "тип 2"  
  
 Преобразование из *type1* в *type2* не являлось более непосредственно, чем любое другое.  Рекомендуется ознакомиться 2 возможного решения к преобразованию *type1* в *type2*.  Первый вариант предполагает определение прямого преобразования из *type1* в *type2*, а второй параметр указать последовательность преобразований из *type1* в *type2*.  
  
 Следующий пример демонстрирует причины возникновения ошибки C2594.  Предложенный способ устранения данной ошибки представляет собой последовательность преобразований:  
  
```  
// C2594.cpp  
// compile with: /c  
struct A{};  
struct I1 : A {};  
struct I2 : A {};  
struct D : I1, I2 {};  
  
A *f (D *p) {  
   return (A*) (p);    // C2594  
  
// try the following line instead  
// return static_cast<A *>(static_cast<I1 *>(p));  
}  
```