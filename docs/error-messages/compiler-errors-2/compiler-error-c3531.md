---
title: "Ошибка компилятора C3531 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3531
dev_langs: C++
helpviewer_keywords: C3531
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7753e30e305b7b36adc3b4d2b535f755fa455bdd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3531"></a>Ошибка компилятора C3531
«символ»: символ, тип которого содержит «auto» должно иметь инициализатор  
  
 Указанная переменная не имеет выражения инициализатора.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Укажите выражение инициализатора, например простого присваивания, который использует синтаксис со знаком равенства, при объявлении переменной.  
  
## <a name="example"></a>Пример  
 Следующий пример вызывает ошибку C3531, поскольку переменные `x1`, `y1, y2, y3`, и `z2` не инициализированы.  
  
```  
// C3531.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto x1;                  // C3531  
   auto y1, y2, y3;          // C3531  
   auto z1 = 1, z2, z3 = -1; // C3531  
   return 0;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Ключевое слово auto](../../cpp/auto-keyword.md)