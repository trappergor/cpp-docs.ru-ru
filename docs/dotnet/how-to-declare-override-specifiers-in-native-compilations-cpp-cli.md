---
title: "Практическое руководство. Объявление спецификаторов переопределения в компиляциях машинного кода (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "спецификаторы переопределения в компиляции машинного кода, переопределение"
ms.assetid: d0551836-9ac7-41eb-a6e9-a4b3ef60767d
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Объявление спецификаторов переопределения в компиляциях машинного кода (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[запечатанный](../windows/sealed-cpp-component-extensions.md) [переопределенный](../windows/override-cpp-component-extensions.md), [abstract](../windows/abstract-cpp-component-extensions.md) и доступны в компиляциях, которые не используют **\/ZW** или [\/clr](../build/reference/clr-common-language-runtime-compilation.md).  
  
> [!NOTE]
>  Речь расширением парадигмы и ISO стандартного языка C \+\+11 идентификатором [переопределенный](../cpp/override-specifier.md) и идентификатор [final](../cpp/final-specifier.md), и оба поддерживаются в использовании `final` Visual Studio вместо `sealed` в коде, не была компилироваться только для уроженц.  
  
## Пример  
  
### Описание  
 В следующем примере показано, `sealed` допустимо в собственных компиляциях.  
  
### Код  
  
```  
// sealed_native_keyword.cpp  
#include <stdio.h>  
__interface I1 {  
   virtual void f();  
   virtual void g();  
};  
  
class X : public I1 {  
public:  
   virtual void g() sealed {}  
};  
  
class Y : public X {  
public:  
  
   // the following override generates a compiler error  
   virtual void g() {}   // C3248 X::g is sealed!  
};  
```  
  
## Пример  
  
### Описание  
 В следующем примере показано, `override` допустимо в собственных компиляциях.  
  
### Код  
  
```  
// override_native_keyword.cpp  
#include <stdio.h>  
__interface I1 {  
   virtual void f();  
};  
  
class X : public I1 {  
public:  
   virtual void f() override {}   // OK  
   virtual void g() override {}   // C3668 I1::g does not exist  
};  
```  
  
## Пример  
  
### Описание  
 В этом примере показано, `abstract` допустимо в собственных компиляциях.  
  
### Код  
  
```  
// abstract_native_keyword.cpp  
class X abstract {};  
  
int main() {  
   X * MyX = new X;   // C3622 cannot instantiate abstract class  
}  
```  
  
## См. также  
 [Спецификаторы переопределения](../windows/override-specifiers-cpp-component-extensions.md)