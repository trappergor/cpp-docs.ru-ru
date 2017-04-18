---
title: "Ошибка компилятора C3490 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3490
dev_langs:
- C++
helpviewer_keywords:
- C3490
ms.assetid: 7638559a-fd06-4527-a9c1-0c8ae68b3123
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 83a215b1c4883ba7ed4b285af8c4efafe2cfaa05
ms.lasthandoff: 04/04/2017

---
# <a name="compiler-error-c3490"></a>Ошибка компилятора C3490
"переменная" не может быть изменен, поскольку доступ к нему осуществляется через константный объект  
  
 Лямбда-выражение, объявленное в методе `const` , не может изменять данные недоступного для изменения члена.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите модификатор `const` из объявления метода.  
  
## <a name="example"></a>Пример  
 Следующий пример вызывает ошибку C3490, так как она изменяет переменной-члена `_i` в `const` метод:  
  
```  
// C3490a.cpp  
// compile with: /c  
  
class C  
{  
   void f() const   
   {  
      auto x = [=]() { _i = 20; }; // C3490  
   }  
  
   int _i;  
};  
```  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере ошибка C3490 устраняется путем удаления модификатора `const` из объявления метода.  
  
```  
// C3490b.cpp  
// compile with: /c  
  
class C  
{  
   void f()  
   {  
      auto x = [=]() { _i = 20; };  
   }  
  
   int _i;  
};  
```  
  
## <a name="see-also"></a>См. также  
 [Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)
