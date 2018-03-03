---
title: "Ошибка компилятора C3228 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3228
dev_langs:
- C++
helpviewer_keywords:
- C3228
ms.assetid: 9015adf9-17b0-4312-b4a7-c1f33e4126f4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8da9a3cd70f532cdac27a50b1164600ae63764b2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3228"></a>Ошибка компилятора C3228
"функция": аргумент универсального типа для param не может быть типа "тип", он должен иметь тип значения или тип дескриптора  
  
 Неправильный тип был передан в качестве аргумента универсального типа.  
  
 В следующем примере возникает ошибка C3228:  
  
```  
// C3228.cpp  
// compile with: /clr  
class A {};  
  
value class B {};  
  
generic <class T>  
void Test() {}  
  
ref class C {  
public:  
   generic <class T>  
   static void f() {}  
};  
  
int main() {  
   C::f<A>();   // C3228  
   C::f<B>();   // OK  
  
   Test<C>();   // C3228  
   Test<C ^>();   // OK  
}  
```