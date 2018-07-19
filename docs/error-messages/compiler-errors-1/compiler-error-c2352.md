---
title: Ошибка компилятора C2352 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2352
dev_langs:
- C++
helpviewer_keywords:
- C2352
ms.assetid: 0efad8cb-659f-4b3e-8f6f-9f8ec44d345c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8a0ed1942051929b4f1ba3391be0ceead7a75586
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33196170"
---
# <a name="compiler-error-c2352"></a>Ошибка компилятора C2352
class::function: недопустимый вызов нестатической функции-члена  
  
 Функция-член `static` вызвала нестатическую функцию-член. Или нестатическая функция-член была вызвана извне класса в качестве статической функции.  
  
 В следующем примере показано возникновение ошибки C2352 и приводятся сведения по ее устранению.  
  
```  
// C2352.cpp  
// compile with: /c  
class CMyClass {  
public:  
   static void func1();  
   void func2();  
   static void func3() {  
      func2();   // C2352 calls nonstatic func2  
      func1();   // OK calls static func1  
   }  
};  
```  
  
 В следующем примере показано возникновение ошибки C2352 и приводятся сведения по ее устранению.  
  
```  
// C2352b.cpp  
class MyClass {  
public:  
   void MyFunc() {}  
   static void MyFunc2() {}  
};  
  
int main() {  
   MyClass::MyFunc();   // C2352  
   MyClass::MyFunc2();   // OK  
}  
```