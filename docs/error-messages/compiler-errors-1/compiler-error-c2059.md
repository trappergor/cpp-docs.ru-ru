---
title: "Ошибка компилятора C2059 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2059
dev_langs: C++
helpviewer_keywords: C2059
ms.assetid: 2be4eb39-3f37-4b32-8e8d-75835e07c78a
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dbf80ab803eaaacc29ac82657af130194417f1c7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2059"></a>Ошибка компилятора C2059
Синтаксическая ошибка: «лексема»  
  
 Токен является причиной синтаксической ошибки.  
  
 В следующем примере возникает сообщение об ошибке для строки, которая объявляет `j`.  
  
```  
// C2059e.cpp  
// compile with: /c  
// C2143 expected  
// Error caused by the incorrect use of '*'.  
   int j*; // C2059   
```  
  
 Чтобы определить причину ошибки, проверьте, не только строки, которая указана в сообщении об ошибке, но и строки выше нее. Если проверка строк не проясняет о проблеме, попробуйте закомментировать строку, которая указана в сообщении об ошибке и может быть несколько строк, над ним.  
  
 Если появляется сообщение об ошибке на символ, который следует сразу за `typedef` переменной, убедитесь, что переменная определена в исходном коде.  
  
 C2059 может возникать, если символ раскрывается в пустую строку, что может происходить, когда **/D** `symbol`  **=**  используется для компиляции.  
  
```  
// C2059a.cpp  
// compile with: /DTEST=  
#include <stdio.h>  
  
int main() {  
   #ifdef TEST  
      printf_s("\nTEST defined %d", TEST);   // C2059  
   #else  
      printf_s("\nTEST not defined");  
   #endif  
}  
```  
  
 Другой случай, в котором может возникнуть C2059, при компиляции приложения, которое определяет структуру, в аргументы по умолчанию для функции. Значение по умолчанию для аргумента должно быть выражение. Список инициализаторов — например, тот, который используется для инициализации структуры, не является выражением.  Чтобы устранить эту проблему, определите конструктор для выполнения инициализации.  
  
 Следующий пример приводит к возникновению ошибки C2059:  
  
```  
// C2059b.cpp  
// compile with: /c  
struct ag_type {  
   int a;  
   float b;  
   // Uncomment the following line to resolve.  
   // ag_type(int aa, float bb) : a(aa), b(bb) {}   
};  
  
void func(ag_type arg = {5, 7.0});   // C2059  
void func(ag_type arg = ag_type(5, 7.0));   // OK  
```  
  
 Можно также получить C2059 при определении члена шаблонного класса или функции вне класса. Сведения см. в разделе [статьи базы знаний 241949](http://support.microsoft.com/kb/241949).  
  
 C2059 может произойти некорректное приведения.  
  
 Следующий пример приводит к возникновению ошибки C2059:  
  
```  
// C2059c.cpp  
// compile with: /clr  
using namespace System;  
ref class From {};  
ref class To : public From {};  
  
int main() {  
   From^ refbase = gcnew To();  
   To^ refTo = safe_cast<To^>(From^);   // C2059  
   To^ refTo2 = safe_cast<To^>(refbase);   // OK  
}  
```  
  
 C2059 также может возникать при попытке создания пространства имен, который содержит точку.  
  
 Следующий пример приводит к возникновению ошибки C2059:  
  
```  
// C2059d.cpp  
// compile with: /c  
namespace A.B {}   // C2059  
  
// OK  
namespace A  {  
   namespace B {}  
}  
```  
  
 C2059 может возникнуть, когда оператор, который можно указать имя (`::`, `->`, и `.`) следует указать ключевое слово `template`, как показано в следующем примере:  
  
```cpp  
template <typename T> struct Allocator {  
    template <typename U> struct Rebind {  
        typedef Allocator<U> Other;  
    };  
};  
  
template <typename X, typename AY> struct Container {  
    typedef typename AY::Rebind<X>::Other AX; // error C2059  
};  
  
```  
  
 По умолчанию C++ предполагает, что `AY::Rebind` не является шаблоном; таким образом, следующее `<` интерпретируется как меньше-знак "больше".  Необходимо сообщить компилятор явно, `Rebind` — это шаблон, чтобы он мог правильно интерпретировать знак угловой скобкой. Чтобы исправить эту ошибку, используйте `template` ключевое слово в зависимом типе имени, как показано ниже:  
  
```cpp  
template <typename T> struct Allocator {  
    template <typename U> struct Rebind {  
        typedef Allocator<U> Other;  
    };  
};  
  
template <typename X, typename AY> struct Container {  
    typedef typename AY::template Rebind<X>::Other AX; // correct  
};  
  
```