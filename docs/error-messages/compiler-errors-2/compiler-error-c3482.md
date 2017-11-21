---
title: "Ошибка компилятора C3482 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3482
dev_langs: C++
helpviewer_keywords: C3482
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b19769a8a326613401263fa7700b85c36a9dbbe1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3482"></a>Ошибка компилятора C3482
"this" может быть использован в качестве передаваемого параметра в лямбда-выражении только с нестатической функцией-членом  
  
 Нельзя передавать `this` в список передаваемых параметров лямбда-выражения, объявленного в статическом методе или в глобальной функции.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Преобразуйте включающую функцию в нестатический метод или  
  
-   удалите указатель `this` из списка передаваемых параметров лямбда-выражения.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению предупреждения C3482:  
  
```  
// C3482.cpp  
// compile with: /c  
  
class C  
{  
public:  
   static void staticMethod()  
   {  
      [this] {}(); // C3482  
   }  
};  
```  
  
## <a name="see-also"></a>См. также  
 [Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)