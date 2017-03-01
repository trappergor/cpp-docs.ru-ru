---
title: "C2355 Ошибка компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2355
dev_langs:
- C++
helpviewer_keywords:
- C2355
ms.assetid: 0a947881-d61f-4f98-8409-32140f39500b
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 84bcd1b30bd5009d3f59c48b7daedbb09a529b53
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2355"></a>Ошибка компилятора C2355
this: может указываться только в нестатических функциях-членах или инициализаторах нестатических членов данных  
  
 Указатель `this` действителен только в нестатических функциях-членах или инициализаторах нестатических членов данных. Эта ошибка может возникнуть, когда неправильно квалифицировано определение области класса для функции-члена вне объявления класса. Эта ошибка также может возникнуть, когда указатель `this` используется в функции, которая не объявлена в классе.  
  
 Чтобы устранить эту проблему, убедитесь, что определение функции-члена соответствует объявлению функции-члена в классе и что она не объявлена как статическая. Для инициализаторов членов данных убедитесь, что член данных не объявлен как статический.  
  
 В следующем примере показано возникновение ошибки C2355 и приводятся сведения по ее устранению.  
  
```  
// C2355.cpp  
// compile with: /c  
class MyClass {};  
MyClass *p = this;   // C2355  
  
// OK  
class MyClass2 {  
public:  
   void Test() {  
      MyClass2 *p = this;  
   }  
};  
```
