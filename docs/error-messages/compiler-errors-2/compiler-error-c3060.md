---
title: "Ошибка компилятора C3060 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3060
dev_langs:
- C++
helpviewer_keywords:
- C3060
ms.assetid: 6282bb92-0546-4b59-9435-d3840bf93bdb
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 528ce6f8b94d73acde2a92412c6f3578dd83b4bd
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3060"></a>Ошибка компилятора C3060
"член": дружественную функцию нельзя определить внутри класса с помощью полного имени (ее можно только объявить)  
  
 Дружественная функция была определена с помощью полного имени, что не допускается.  
  
 В следующем примере возникает ошибка C3060.  
  
```  
// C3060.cpp  
class A {  
public:  
   void func();  
};  
  
class C {  
public:  
   friend void A::func() { }   // C3060  
   // Try the following line and the out of class definition:  
   // friend void A::func();  
};  
  
// void A::func(){}  
```
