---
title: "__clrcall | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__clrcall"
  - "__clrcall_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__clrcall - ключевое слово [C++]"
ms.assetid: 92096695-683a-40ed-bf65-0c8443572152
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __clrcall
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Указывает, что функцию можно вызвать только из управляемого кода.  Используйте `__clrcall` для всех виртуальных функций, которые будут вызываться только из управляемого кода.  Однако это соглашение о вызовах невозможно использовать для функций, которые будут вызываться из машинного кода.  
  
 С помощью `__clrcall` можно повысить производительность при вызове из управляемой функции в виртуальную управляемую функцию или из управляемой функции в управляемую функцию с помощью указателя.  
  
 Точки входа представляют собой отдельные функции, создаваемые компилятором.  Если функция имеет машинные и управляемые точки входа, одна из них будет фактической функцией с реализацией функции.  Другая функция будет отдельной функцией \(преобразователем\), которая вызывает фактическую функцию и позволяет среде CLR выполнять PInvoke.  Если функция отмечена как `__clrcall`, это значит, что реализация функции должна быть MSIL и что функция машинной точки входа не создается.  
  
 При получении адреса собственной функции, если функция `__clrcall` не определена, компилятор использует машинную точку входа.  `__clrcall` указывает, что функция является управляемой и нет необходимости выполнять преобразование из управляемой функции в собственную.  В этом случае компилятор использует управляемую точку входа.  
  
 Если используется **\/clr** \(не **\/clr:pure** или **\/clr:safe**\) и не используется `__clrcall`, при получении адреса функции всегда возвращается адрес функции машинной точки входа.  При использовании `__clrcall` функция машинной точки входа не создается, поэтому получается адрес управляемой функции, а не функция преобразователя точки входа.  Дополнительные сведения см. в разделе [Двойное преобразование](../Topic/Double%20Thunking%20\(C++\).md).  
  
 [\/clr \(компиляция CLR\)](../build/reference/clr-common-language-runtime-compilation.md) подразумевает, что все функции и указатели функций являются `__clrcall` и компилятор не позволит отметить функцию в единице компиляции иначе, чем `__clrcall`.  Если используется **\/clr:pure**, `__clrcall` можно определить только в указателях функций и внешних объявлениях.  
  
 Можно явно вызвать функции `__clrcall` из существующего кода C\+\+, который был скомпилирован с помощью **\/clr**, пока функция имеет реализацию MSIL.  Функции `__clrcall` невозможно вызвать непосредственно из функций, которые имеют встроенный код на языке ассемблера и вызывают зависящие от ЦП встроенные функции, даже если эти функции скомпилированы с помощью **\/clr**.  
  
 Указатели функций `__clrcall` предназначены для использования только в домене приложения, в котором они были созданы.  Вместо передачи указателей функций `__clrcall` между доменами приложения используйте <xref:System.CrossAppDomainDelegate>.  Дополнительные сведения см. в разделе [Домены приложений и Visual C\+\+](../dotnet/application-domains-and-visual-cpp.md).  
  
## Пример  
  
```  
// clrcall.cpp  
// compile with: /clr:oldSyntax /LD  
void __clrcall Test1( ) {}  
void (__clrcall *fpTest1)( ) = &Test1;  
```  
  
## Пример  
 Обратите внимание, что если функция объявляется с помощью `__clrcall`, код создается при необходимости, например, при вызове функции.  
  
```  
// clrcall2.cpp  
// compile with: /clr  
using namespace System;  
int __clrcall Func1() {  
   Console::WriteLine("in Func1");  
   return 0;  
}  
  
// Func1 hasn't been used at this point (code has not been generated),   
// so runtime returns the adddress of a stub to the function  
int (__clrcall *pf)() = &Func1;  
  
// code calls the function, code generated at difference address  
int i = pf();   // comment this line and comparison will pass  
  
int main() {  
   if (&Func1 == pf)  
      Console::WriteLine("&Func1 == pf, comparison succeeds");  
   else   
      Console::WriteLine("&Func1 != pf, comparison fails");  
  
   // even though comparison fails, stub and function call are correct  
   pf();  
   Func1();  
}  
```  
  
  **в Func1**  
**&Func1\! \= pf сравнение завершится с ошибкой**  
**в Func1**  
**в Func1**   
## Пример  
 В следующем примере показано, что можно определить указатель функции, например объявить, что указатель функции будет вызываться только из управляемого кода.  Это позволит компилятору непосредственно вызвать управляемую функцию и избежать машинной точки входа \(проблема двойного преобразования\).  
  
```  
// clrcall3.cpp  
// compile with: /clr  
void Test() {  
   System::Console::WriteLine("in Test");  
}  
  
int main() {  
   void (*pTest)() = &Test;  
   (*pTest)();  
  
   void (__clrcall *pTest2)() = &Test;  
   (*pTest2)();  
}  
```  
  
## См. также  
 [Передача аргументов и соглашения именования](../Topic/Argument%20Passing%20and%20Naming%20Conventions.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)