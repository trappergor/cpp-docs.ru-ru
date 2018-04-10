---
title: Заданные пользователем преобразования (C + +/ CLI) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- user-defined conversions [C++]
ms.assetid: 8010fd59-2775-4e9a-a6ed-58055032d66f
caps.latest.revision: 15
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 329461338579dc0787c6e3d208abac89ec762004
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="user-defined-conversions-ccli"></a>заданные пользователем преобразования (C++/CLI)
В этом разделе рассматриваются заданные пользователем преобразования (UDC) при выполнении одного из типов для преобразования ссылку или экземпляр типа значения или ссылочным типом.  
  
## <a name="implicit-and-explicit-conversions"></a>Явные и неявные преобразования  
 Определенное пользователем преобразование может быть явным или неявным.  UDC должно быть неявное, если преобразование не приводит к потере данных. В противном случае явной UDC должен быть определен.  
  
 Экземпляр собственного класса конструктор может использоваться для преобразования типов значений и ссылок на собственный класс.  
  
 Дополнительные сведения о преобразованиях см. в разделе [упаковка-преобразование](../windows/boxing-cpp-component-extensions.md) и [стандартные преобразования](../cpp/standard-conversions.md).  
  
```  
// mcpp_User_Defined_Conversions.cpp  
// compile with: /clr  
#include "stdio.h"  
ref class R;  
class N;  
  
value class V {  
   static operator V(R^) {  
      return V();  
   }  
};  
  
ref class R {  
public:  
   static operator N(R^);  
   static operator V(R^) {  
      System::Console::WriteLine("in R::operator N");  
      return V();  
   }  
};  
  
class N {  
public:  
   N(R^) {  
      printf("in N::N\n");  
   }  
};  
  
R::operator N(R^) {  
   System::Console::WriteLine("in R::operator N");  
   return N(nullptr);  
}  
  
int main() {  
   // Direct initialization:  
   R ^r2;  
   N n2(r2);   // direct initialization, calls constructor  
   static_cast<N>(r2);   // also direct initialization  
  
   R ^r3;  
   // ambiguous V::operator V(R^) and R::operator V(R^)  
   // static_cast<V>(r3);     
}  
```  
  
 **Вывод**  
  
```Output  
in N::N  
in N::N  
```  
  
## <a name="convert-from-operators"></a>Операторы "преобразования из"  
 Операторы преобразования из объекта класса, в котором определен оператор создать из объекта другого класса.  
  
 Стандарт C++ не поддерживает преобразования из операторы; Стандартный язык C++ использует конструкторы для этой цели. Тем не менее при использовании типов CLR, Visual C++ поддерживают синтаксический операторы преобразования из вызова.  
  
 Для взаимодействия с другими языками CLS-совместимым, вы можете обернуть соответствующий оператор преобразования из каждого унарный определяемого пользователем конструктора для данного класса.  
  
 Операторы преобразования из:  
  
-   Должны быть определены как статические функции.  
  
-   Либо можно (для преобразования, без потери точности, такие как тип short int) явные и неявные, когда может быть потеря точности.  
  
-   Должна возвращать объект одного из включающего класса.  
  
-   Должен иметь тип «от» в качестве единственного параметра типа.  
  
 В следующем примере показано явное и неявное «преобразования из», оператор определенного пользователем преобразования (UDC).  
  
```  
// clr_udc_convert_from.cpp  
// compile with: /clr  
value struct MyDouble {  
   double d;  
  
   MyDouble(int i) {  
      d = static_cast<double>(i);  
      System::Console::WriteLine("in constructor");  
   }  
  
   // Wrap the constructor with a convert-from operator.  
   // implicit UDC because conversion cannot lose precision  
   static operator MyDouble (int i) {  
      System::Console::WriteLine("in operator");  
      // call the constructor  
      MyDouble d(i);  
      return d;  
   }  
  
   // an explicit user-defined conversion operator  
   static explicit operator signed short int (MyDouble) {  
      return 1;  
   }  
};  
  
int main() {  
   int i = 10;  
   MyDouble md = i;  
   System::Console::WriteLine(md.d);  
  
   // using explicit user-defined conversion operator requires a cast    
   unsigned short int j = static_cast<unsigned short int>(md);  
   System::Console::WriteLine(j);  
}  
```  
  
 **Вывод**  
  
```Output  
in operator  
in constructor  
10  
1  
```  
  
## <a name="convert-to-operators"></a>Операторы преобразования в  
 Операторы преобразования в преобразование объекта класса, в котором определен оператор, либо другого объекта. В следующем примере показано неявное, преобразования в, определенный пользователем оператор преобразования:  
  
```  
// clr_udc_convert_to.cpp  
// compile with: /clr  
using namespace System;  
value struct MyInt {  
   Int32 i;  
  
   // convert MyInt to String^  
   static operator String^ ( MyInt val ) {  
      return val.i.ToString();  
   }  
  
   MyInt(int _i) : i(_i) {}  
};  
  
int main() {  
   MyInt mi(10);  
   String ^s = mi;  
   Console::WriteLine(s);  
}  
```  
  
 **Вывод**  
  
```Output  
10  
```  
  
 Оператор преобразования явные пользовательские преобразования в подходит для преобразования, потерять данные определенным образом. Чтобы вызвать явного оператора convert, необходимо использовать приведение.  
  
```  
// clr_udc_convert_to_2.cpp  
// compile with: /clr  
value struct MyDouble {  
   double d;  
   // convert MyDouble to Int32  
   static explicit operator System::Int32 ( MyDouble val ) {  
      return (int)val.d;  
   }  
};  
  
int main() {  
   MyDouble d;  
   d.d = 10.3;  
   System::Console::WriteLine(d.d);  
   int i = 0;  
   i = static_cast<int>(d);  
   System::Console::WriteLine(i);  
}  
```  
  
 **Вывод**  
  
```Output  
10.3  
10  
```  
  
## <a name="to-convert-generic-classes"></a>Для преобразования универсальных классов  
 Универсальный класс можно преобразовать в T.  
  
```  
// clr_udc_generics.cpp  
// compile with: /clr  
generic<class T>   
public value struct V {  
   T mem;  
   static operator T(V v) {  
      return v.mem;  
   }  
  
   void f(T t) {  
      mem = t;  
   }  
};  
  
int main() {  
   V<int> v;  
   v.f(42);  
   int i = v;  
   i += v;  
   System::Console::WriteLine(i == (42 * 2) );  
}  
```  
  
 **Вывод**  
  
```Output  
True  
```  
  
 Преобразование конструктор принимает значение типа и использует его для создания объекта.  Преобразование конструктор вызывается с прямой инициализации. приведения типов не будет вызывать конструкторы преобразования. По умолчанию конструкторах преобразования являются явными для типов CLR.  
  
```  
// clr_udc_converting_constructors.cpp  
// compile with: /clr  
public ref struct R {  
   int m;  
   char c;  
  
   R(int i) : m(i) { }  
   R(char j) : c(j) { }  
};  
  
public value struct V {  
   R^ ptr;  
   int m;  
  
   V(R^ r) : ptr(r) { }  
   V(int i) : m(i) { }  
};  
  
int main() {   
   R^ r = gcnew R(5);  
  
   System::Console::WriteLine( V(5).m);  
   System::Console::WriteLine( V(r).ptr);  
}  
```  
  
 **Вывод**  
  
```Output  
5  
R  
```  
  
 В этом примере кода функция неявное преобразование статических выполняет то же, что явного конструктора преобразования.  
  
```  
public value struct V {  
   int m;  
   V(int i) : m(i) {}  
   static operator V(int i) {  
      V v(i*100);  
      return v;  
   }  
};  
  
public ref struct R {  
   int m;  
   R(int i) : m(i) {}  
   static operator R^(int i) {  
      return gcnew R(i*100);  
   }  
};  
  
int main() {  
   V v(13);   // explicit  
   R^ r = gcnew R(12);   // explicit  
  
   System::Console::WriteLine(v.m);  
   System::Console::WriteLine(r->m);  
  
   // explicit ctor can't be called here: not ambiguous  
   v = 5;  
   r = 20;  
  
   System::Console::WriteLine(v.m);  
   System::Console::WriteLine(r->m);  
}  
```  
  
 **Вывод**  
  
```Output  
13  
12  
500  
2000  
```  
  
## <a name="see-also"></a>См. также  
 [Классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md)