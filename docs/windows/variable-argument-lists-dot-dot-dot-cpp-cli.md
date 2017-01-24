---
title: "Списки аргументов переменных (...) (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "массивы параметров"
  - "списки аргументов переменных"
ms.assetid: db1a27f4-02a8-4318-8690-1f2893f52b38
caps.latest.revision: 22
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Списки аргументов переменных (...) (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этом примере показано, как можно использовать синтаксис `...` в Visual C\+\+ для реализации функций, которые содержат переменное число аргументов.  
  
> [!NOTE]
>  Этот раздел относится к C\+\+\/CLI.  Сведения об использовании `...` C\+\+ стандарта ISO см. в разделах [Многоточия и шаблоны с переменными аргументами](../cpp/ellipses-and-variadic-templates.md) и [Многоточия и аргументы по умолчанию](../misc/ellipses-and-default-arguments.md).  
  
 Параметр, использующий `...`, должен быть последним в списке параметров.  
  
## Пример  
  
### Код  
  
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
  
### Output  
  
```  
3  
```  
  
## Пример кода  
 В следующем примере показано, как вызывать в C\# функции Visual C\+\+, которая принимает переменное число аргументов.  
  
```  
// mcppv2_paramarray2.cpp  
// compile with: /clr:safe /LD  
using namespace System;  
  
public ref class C {  
public:   
   void f( ... array<String^>^ a ) {}  
};  
```  
  
 Функция `f` можно вызывать в C\# или Visual Basic, например, как если бы она была функцией, которая может принимать переменное число аргументов.  
  
 В C\# аргумент, который передается в параметр `ParamArray`, может вызываться переменным количеством аргументов.  Ниже приведен пример кода на C\#.  
  
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
  
 Вызов `f` в Visual C\+\+ может передать инициализированный массив или массив переменной длины.  
  
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
  
## См. также  
 [Массивы](../windows/arrays-cpp-component-extensions.md)