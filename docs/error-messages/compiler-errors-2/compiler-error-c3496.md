---
title: "Ошибка компилятора C3496 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3496
dev_langs:
- C++
helpviewer_keywords:
- C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 86c80c4b708bd4315b2ce2ceaf7b61e0629a8b2e
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3496"></a>Ошибка компилятора C3496
"this" всегда передается по значению: знак "&" проигнорирован  
  
 Нельзя передать указатель `this` по ссылке.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Передайте указатель `this` по значению.  
  
## <a name="example"></a>Пример  
 Представленный ниже пример приводит к возникновению ошибки C3496, так как ссылка на указатель `this` присутствует в списке передачи лямбда-выражения.  
  
```  
// C3496.cpp  
// compile with: /c  
  
class C  
{  
   void f()  
   {  
      [&this] {}(); // C3496  
   }  
};  
```  
  
## <a name="see-also"></a>См. также  
 [Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)
