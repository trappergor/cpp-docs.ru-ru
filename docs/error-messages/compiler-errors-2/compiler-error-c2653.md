---
title: "Ошибка компилятора C2653 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2653
dev_langs:
- C++
helpviewer_keywords:
- C2653
ms.assetid: 3f49e731-affd-43a0-a8d0-181db7650bc3
caps.latest.revision: 9
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
ms.sourcegitcommit: eb0c1bf407d1478451c246cf615d031ef6c45bf9
ms.openlocfilehash: 2203cf8a09dbb05f6145ed238ab9fc03e458aaa5
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2653"></a>Ошибка компилятора C2653
«Идентификатор»: не является именем класса или пространства имен  
  
Синтаксис требует класса, структуры, объединения или пространства имен.  
  
Следующий пример приводит к возникновению ошибки C2653:  
  
```cpp  
// C2653.cpp  
// compile with: /c  
class yy {  
   void func1(int i);  
};  
  
void xx::func1(int m) {}   // C2653  
void yy::func1(int m) {}   // OK  
```  
  
C2653 можно также при попытке определить *составных имен*, пространство имен, содержащее одно или несколько имен вложенной области видимости пространства имен, при использовании версии Visual C++ до Visual Studio 2015 г. обновление 3. Составное пространство имен определения, не разрешены в C++ до C ++&17;. Начиная с Visual C++ 2015 г. обновление 3, компилятор поддерживает составное пространство имен определения при [/std:c ++ последнюю](../../build/reference/std-specify-language-standard-version.md) указан параметр компилятора:  
```cpp  
// C2653b.cpp  
namespace a::b {int i;}   // C2653 prior to Visual C++ 2015 Update 3,  
                          // C2429 thereafter. Use /std:c++latest to fix.
namespace a {  
   namespace b {  
      int i;  
   }  
}  
  
int main() {  
   a::b::i = 2;  
}  
```  
