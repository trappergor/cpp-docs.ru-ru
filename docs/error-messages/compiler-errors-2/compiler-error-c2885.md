---
title: Ошибка компилятора C2885 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2885
dev_langs:
- C++
helpviewer_keywords:
- C2885
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f37ea0f9fadb74b44eea5ad110f7f12b884f0e41
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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