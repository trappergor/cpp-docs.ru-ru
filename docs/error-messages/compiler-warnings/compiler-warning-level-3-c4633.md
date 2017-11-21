---
title: "Предупреждение (уровень 3) C4633 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4633
dev_langs: C++
helpviewer_keywords: C4633
ms.assetid: 6d76f268-ba8c-448b-8e83-b903a18b583b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a3b3edf09a899ee44ea056064d8e05c5f21a3afc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4633"></a>Предупреждение компилятора (уровень 3) C4633
Цель комментария XML-документа: ошибка: причина  
  
 Имя, переданное [ \<param >](../../ide/param-visual-cpp.md) компилятором не найден тег.  
  
 Следующий пример приводит к возникновению ошибки C4633:  
  
```  
// C4633.cpp  
// compile with: /clr /doc /LD /W3  
  
/// Text for class MyClass.  
public ref class MyClass {  
   // C4633 remove line for Int3  
   /// <param name="Int1">Used to indicate status.</param>  
   /// <param name="Int3">Used to indicate status.</param>  
   void MyMethod(int Int1) {  
      Int1 = 0;  
      Int1++;  
   }  
};  
```