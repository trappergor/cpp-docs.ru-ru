---
title: "Ошибка компилятора C2355 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 76d274ee94c20502a0ca6f167a9fce1f1dbf9465
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

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
