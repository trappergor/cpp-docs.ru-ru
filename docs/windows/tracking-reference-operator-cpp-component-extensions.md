---
title: Оператор отслеживания ссылок (расширения компонентов C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- '%'
dev_langs:
- C++
helpviewer_keywords:
- tracking references
- '% tracking reference [C++]'
ms.assetid: 142a7269-ab69-4b54-a6d7-833bef06228f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c460174fad6a287acfd434b1589e73153aa0b121
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="tracking-reference-operator-c-component-extensions"></a>Оператор отслеживания ссылок (расширения компонентов C++)
Объект *отслеживаемая ссылка* (`%`) ведет себя как обычная ссылка C++ (`&`) за исключением того, когда объекту назначается отслеживаемую ссылку, счетчик ссылок объекта увеличивается.  
  
## <a name="all-platforms"></a>Все платформы  
 Отслеживаемая ссылка имеет следующие характеристики:  
  
-   Присвоение объекту отслеживаемой ссылки увеличивает счетчик ссылок объекта.  
  
-   Собственная ссылка (&) — это результат разыменования *. Отслеживаемая ссылка (%) — это результат разыменования ^. Пока имеется ссылка на объект (%), он будет оставаться в памяти в активном состоянии.  
  
-   Оператор доступа к членам "точка" (`.`) используется для обращения к членам объекта.  
  
-   Отслеживаемые ссылки являются допустимыми для типов значений и дескрипторов (например, `String^`).  
  
-   Отслеживаемой ссылке невозможно присвоить значение NULL или `nullptr`. Отслеживаемая ссылка может быть переприсвоена другому допустимому объекту любое число раз при необходимости.  
  
-   Отслеживаемую ссылку невозможно использовать в качестве унарного оператора получения адреса.  
  
## <a name="windows-runtime"></a>Среда выполнения Windows  
 Отслеживаемая ссылка ведет себя как стандартная ссылка C++, за исключением того, что % учитывается при подсчете ссылок. В следующем фрагменте кода показано, как выполнять преобразование между типами % и ^:  
  
```  
Foo^ spFoo = ref new Foo();  
Foo% srFoo = *spFoo;  
Foo^ spFoo2 = %srFoo;  
```  
  
 В следующем примере показан способ передачи ^ в функцию, которая принимает %.  
  
```  
  
ref class Foo sealed {};  
  
    // internal or private  
    void UseFooHelper(Foo% f)  
    {  
        auto x = %f;  
    }  
  
    // public method on ABI boundary  
    void UseFoo(Foo^ f)  
    {  
        if (f != nullptr) { UseFooHelper(*f); }  
    }  
```  
  
## <a name="common-language-runtime"></a>Среда CLR 
 В C++/CLI можно использовать отслеживаемую ссылку на дескриптор при привязке к объекту типа CLR в куче со сборкой мусора.  
  
 В CLR значение переменной отслеживаемой ссылки обновляется автоматически, когда сборщик мусора перемещает указанный объект.  
  
 Отслеживаемая ссылка может быть объявлена только в стеке. Отслеживаемая ссылка не может быть членом класса.  
  
 Невозможно создать собственную ссылку C++ на объект, находящийся в куче со сборкой мусора.  
  
 Дополнительные сведения об отслеживаемых ссылках C++/CLI см. в следующих разделах:  
  
-   [Практическое руководство. Использование отслеживаемых ссылок в C++/CLI](../dotnet/how-to-use-tracking-references-in-cpp-cli.md)
  
### <a name="examples"></a>Примеры  
 **Пример**  
  
 В следующем примере для C++/CLI показано, как использовать отслеживаемые ссылки в собственных и управляемых типах.  
  
```  
// tracking_reference_1.cpp  
// compile with: /clr  
ref class MyClass {  
public:  
   int i;  
};  
  
value struct MyStruct {  
   int k;  
};  
  
int main() {  
   MyClass ^ x = ref new MyClass;  
   MyClass ^% y = x;   // tracking reference handle to reference object   
  
   int %ti = x->i;   // tracking reference to member of reference type  
  
   int j = 0;  
   int %tj = j;   // tracking reference to object on the stack  
  
   int * pi = new int[2];  
   int % ti2 = pi[0];   // tracking reference to object on native heap  
  
   int *% tpi = pi;   // tracking reference to native pointer  
  
   MyStruct ^ x2 = ref new MyStruct;  
   MyStruct ^% y2 = x2;   // tracking reference to value object  
  
   MyStruct z;  
   int %tk = z.k;   // tracking reference to member of value type  
  
   delete[] pi;  
}  
  
```  
  
 **Пример**  
  
 В следующем примере для C++/CLI показано, как привязать отслеживаемую ссылку к массиву.  
  
```  
// tracking_reference_2.cpp  
// compile with: /clr  
using namespace System;  
  
int main() {  
   array<int> ^ a = ref new array<Int32>(5);  
   a[0] = 21;  
   Console::WriteLine(a[0]);  
   array<int> ^% arr = a;  
   arr[0] = 222;  
   Console::WriteLine(a[0]);  
}  
```  
  
 **Вывод**  
  
```Output  
21  
222  
```