---
title: "Ошибка компилятора C2698 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2698
dev_langs: C++
helpviewer_keywords: C2698
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 654367e882b16c18cc4bd58c339d61c653dc68e9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2698"></a>Ошибка компилятора C2698
объявление using для "объявления 1" не могут сосуществовать с существующие объявление using для "объявления 2"  
  
 После получения [объявление using](../../cpp/using-declaration.md) для члена данных, любое с помощью объявления в той же области, которая использует то же имя, не разрешено, как только функции могут быть перегружены.  
  
 Следующий пример приводит к возникновению ошибки C2698:  
  
```  
// C2698.cpp  
struct A {  
   int x;  
};  
  
struct B {  
   int x;  
};  
  
struct C : A, B {  
   using A::x;  
   using B::x;   // C2698  
}  
```