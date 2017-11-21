---
title: "Ошибка компилятора C2653 | Документы Microsoft"
ms.custom: 
ms.date: 11/16/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2653
dev_langs: C++
helpviewer_keywords: C2653
ms.assetid: 3f49e731-affd-43a0-a8d0-181db7650bc3
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8b2cca7e855256e9caf5a72e6f8b4a6e2924eca6
ms.sourcegitcommit: 78f3f8208d49b7c1d87f4240f4a1496b7c29333e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2017
---
# <a name="compiler-error-c2653"></a>Ошибка компилятора C2653
«Идентификатор»: не является именем класса или пространства имен  
  
Синтаксис требует класса, структуры, объединения или имя пространства имен.  
  
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
  
C2653 можно также при попытке определить *составное пространство имен*, пространство имен, которое содержит одно или несколько имен вложенной области видимости пространства имен, при использовании с версии Visual C++ до Visual Studio 2015 с обновлением 3. Составные пространства имен определения не допускаются в C++ до C ++ 17. Начиная с версии Visual C++ 2015 г. версия 15,5, компилятор поддерживает составное пространство имен определения при [/std: c ++ 17](../../build/reference/std-specify-language-standard-version.md) указан параметр компилятора:  
```cpp  
// C2653b.cpp  
namespace a::b {int i;}   // C2653 prior to Visual C++ 2015 Update 3,  
                          // C2429 thereafter. Use /std:c++17 to fix (or /std:c++latest in 15.3)
namespace a {  
   namespace b {  
      int i;  
   }  
}  
  
int main() {  
   a::b::i = 2;  
}  
```  

В Visual Studio 2017 г. версия 15,3, / std: c ++ последний параметр является обязательным.
