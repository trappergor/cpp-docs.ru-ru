---
title: "Списки аргументов переменных (...) (C + +/ CLI) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- variable argument lists
- parameter arrays
ms.assetid: db1a27f4-02a8-4318-8690-1f2893f52b38
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b78b244a93bea0c669c37b5df32ec7146f7ac3b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="variable-argument-lists--ccli"></a>Списки аргументов переменных (...) (C++/CLI)
В этом примере показано, как можно использовать `...` синтаксиса в Visual C++ для реализации функций с переменным числом аргументов.  
  
> [!NOTE]
>  Этот раздел относится к C + +/ CLI. Дополнительные сведения об использовании `...` в языка C++ стандарта ISO, в разделе [многоточия и шаблоны с переменным числом аргументов](../cpp/ellipses-and-variadic-templates.md) и эллипсы и аргументы по умолчанию в [постфиксные выражения](../cpp/postfix-expressions.md).  
  
 Параметр, который использует `...` должен быть последним параметром в списке параметров.  
  
## <a name="example"></a>Пример  
  
### <a name="code"></a>Код  
  
```  
// mcppv2_paramarray.cpp  
// compile with: /clr  
using namespace System;  
double average( ... array<Int32>^ arr ) {  
   int i = arr->GetLength(0);  
   double answer = 0.0;  
  
   for (int j = 0 ; j < i ; j++)  
      answer += arr[j];  
  
   return answer / i;  
}  
  
int main() {  
   Console::WriteLine("{0}", average( 1, 2, 3, 6 ));  
}  
```  
  
### <a name="output"></a>Вывод  
  
```  
3  
```  
  
## <a name="code-example"></a>Пример кода  
 Приведенный ниже показано, как вызвать из C#, Visual C++ функция, которая принимает переменное число аргументов.  
  
```  
// mcppv2_paramarray2.cpp  
// compile with: /clr:safe /LD  
using namespace System;  
  
public ref class C {  
public:   
   void f( ... array<String^>^ a ) {}  
};  
```  
  
 Функция `f` можно вызвать из C# или Visual Basic, например, как если бы он функцию, которая может принимать переменное число аргументов.  
  
 В C#, аргумент, передаваемый `ParamArray` параметра может быть вызван с переменным числом аргументов. В следующем образце кода находится в C#.  
  
```  
// mcppv2_paramarray3.cs  
// compile with: /r:mcppv2_paramarray2.dll  
// a C# program  
  
public class X {  
   public static void Main() {  
      // Visual C# will generate a String array to match the   
      // ParamArray attribute  
      C myc = new C();  
      myc.f("hello", "there", "world");  
   }  
}  
```  
  
 Вызов `f` в Visual C++ можно передать инициализированный массив или массив переменной длины.  
  
```  
// mcpp_paramarray4.cpp  
// compile with: /clr  
using namespace System;  
  
public ref class C {  
public:   
   void f( ... array<String^>^ a ) {}  
};  
  
int main() {  
   C ^ myc = gcnew C();  
   myc->f("hello", "world", "!!!");  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Массивы](../windows/arrays-cpp-component-extensions.md)