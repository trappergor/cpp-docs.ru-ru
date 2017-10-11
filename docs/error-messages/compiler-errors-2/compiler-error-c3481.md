---
title: "Ошибка компилятора C3481 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3481
dev_langs:
- C++
helpviewer_keywords:
- C3481
ms.assetid: 5d09375a-5ed3-4b61-86ed-45e91fd734c7
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 33bd3d85a4cf44741d59ccb81259babd34704b69
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3481"></a>Ошибка компилятора C3481
var: переменная, передаваемая в лямбда-выражение, не найдена  
  
 Компилятору не удалось найти определение переменной, которая передается в список передаваемых параметров в лямбда-выражении.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите переменную из списка передаваемых параметров в лямбда-выражении.  
  
## <a name="example"></a>Пример  
 В следующем примере возникает ошибка C3481, так как переменная `n` не определена:  
  
```  
// C3481.cpp  
  
int main()  
{  
   [n] {}(); // C3481  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)
