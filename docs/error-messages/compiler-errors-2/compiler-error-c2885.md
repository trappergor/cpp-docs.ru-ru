---
title: "Ошибка компилятора C2885 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2885
dev_langs:
- C++
helpviewer_keywords:
- C2885
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 98f3501cc029094d7f00e941026c0f7d1ed7d80b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2885"></a>Ошибка компилятора C2885
«класс::идентификатор»: не недопустимое объявление в область вне класса  
  
 Вы использовали [с помощью](../../cpp/using-declaration.md) объявление неправильно.  
  
## <a name="example"></a>Пример  
 Эта ошибка может возникать в результате действий по обеспечению совместимости компилятора с Visual C++ 2005: больше не допустимо иметь `using` объявление вложенного типа необходимо явно квалифицировать каждой ссылки, внесенные во вложенном типе, поместить тип в имени пробел или создайте typedef.  
  
 Следующий пример приводит к возникновению ошибки C2885.  
  
```  
// C2885.cpp  
namespace MyNamespace {  
   class X1 {};  
}  
  
struct MyStruct {  
   struct X1 {  
      int i;  
   };  
};  
  
int main () {  
   using MyStruct::X1;   // C2885  
  
   // OK  
   using MyNamespace::X1;  
   X1 myX1;  
  
   MyStruct::X1 X12;  
  
   typedef MyStruct::X1 abc;  
   abc X13;  
   X13.i = 9;  
}  
```  
  
## <a name="example"></a>Пример  
 Если вы используете `using` ключевое слово с членом класса C++ необходимо определить этот член внутри другого (производного класса).  
  
 Следующий пример приводит к возникновению ошибки C2885.  
  
```  
// C2885_b.cpp  
// compile with: /c  
class A {  
public:  
   int i;  
};  
  
void z() {  
   using A::i;   // C2885 not in a class  
}  
  
class B : public A {  
public:  
   using A::i;  
};  
```