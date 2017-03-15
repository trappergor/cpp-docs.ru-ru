---
title: "C3772 Ошибка компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3772
dev_langs:
- C++
helpviewer_keywords:
- C3772
ms.assetid: 63e938d4-088d-41cc-a562-5881a05b5710
caps.latest.revision: 13
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
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: 7bf4fc0d7e80d2bd77343ee43c31dc74b93c97de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3772"></a>Ошибка компилятора C3772
"имя": недопустимое объявление дружественного шаблона  
  
Не допускается объявлять дружественный элемент для специализации шаблона класса. Вы не можете объявить в одном операторе явную или частичную специализацию шаблона класса и дружественный элемент для этой специализации. *Имя* идентифицирует недопустимое объявление.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Не объявляйте дружественный элемент для специализации шаблона класса.  
  
-   Если это нужно в вашем приложении, объявите дружественный элемент для шаблона класса либо для конкретной частичной или явной специализации.  
  
## <a name="example"></a>Пример  
 В следующем примере кода произойдет ошибка компиляции из-за объявления дружественного элемента для частичной специализации шаблона класса.  
  
```cpp  
// c3772.cpp  
// compile with: /c  
  
// A class template.  
    template<class T> class A {};  
  
// A partial specialization of the class template.  
    template<class T> class A<T*> {};  
  
// An explicit specialization.  
    template<> class A<char>;  
  
class X {  
// Invalid declaration of a friend of a partial specialization.  
    template<class T> friend class A<T*>; // C3772  
  
// Instead, if it is appropriate for your application, declare a   
// friend of the class template. Consequently, all specializations   
// of the class template are friends:  
//    template<class T> friend class A;  
// Or declare a friend of a particular partial specialization:  
//    friend class A<int*>;  
// Or declare a friend of a particular explicit specialization:  
//    friend class A<char>;  
};  
```  
  
## <a name="see-also"></a>См. также  
[Шаблоны](../../cpp/templates-cpp.md)   
[Специализация шаблона](../../cpp/template-specialization-cpp.md)   

