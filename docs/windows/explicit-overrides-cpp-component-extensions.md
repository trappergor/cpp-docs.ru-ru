---
title: "Явные переопределения (расширения компонентов C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
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
  - "переопределение, переопределение [C++]"
ms.assetid: 4ec3eaf5-163b-4df8-8f16-7a2ec04c3d0f
caps.latest.revision: 21
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Явные переопределения (расширения компонентов C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этом разделе описываются способы явного переопределения члена базового класса или интерфейса.  Именованное \(явное\) переопределение должно использоваться только для переопределения метода производным методом с другим именем.  
  
## Все среды выполнения  
 **Синтаксис**  
  
```  
  
        overriding-function-declarator = type::function [,type::function] { overriding-function-definition }  
overriding-function-declarator = function { overriding-function-definition }  
```  
  
 **Параметры**  
  
 *overriding\-function\-declarator*  
 Возвращаемый тип, имя и список аргументов переопределяющей функции.  Обратите внимание, что переопределяющая функция не должна иметь то же имя, что и переопределяемая функция.  
  
 *type*  
 Базовый тип, содержащий функцию для переопределения.  
  
 *function*  
 Список из одного или нескольких имен функций, которые следует переопределить.  
  
 *overriding\-function\-definition*  
 Операторы тела функции, которые определяют переопределяющую функцию.  
  
 **Примечания**  
  
 Явное переопределение используется для создания псевдонима сигнатуры метода или для предоставления различных реализаций методов с одной и той же сигнатурой.  
  
 Дополнительные сведения об изменении поведения унаследованных типов и членов унаследованных типов см. в разделе [Спецификаторы переопределения](../windows/override-specifiers-cpp-component-extensions.md).  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
  
### Требования  
 Параметр компилятора: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Примечания**  
  
 Дополнительные сведения о явных переопределениях в собственном коде или для кода, компилируемого с использованием параметра **\/clr:oldSyntax** см. в разделе [Явные переопределения](../cpp/explicit-overrides-cpp.md).  
  
### Требования  
 Параметр компилятора: **\/clr**  
  
### Примеры  
 **Пример**  
  
 В следующем примере кода показано простое неявное переопределение и реализация члена базового интерфейса без использования явных переопределений.  
  
```  
// explicit_override_1.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X : public I1 {  
public:  
   virtual void f() {  
      System::Console::WriteLine("X::f override of I1::f");  
   }  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   MyI -> f();  
}  
```  
  
 **Output**  
  
  **X::f override of I1::f** **Пример**  
  
 В следующем примере показано, как реализовать все члены интерфейса с общей сигнатурой, используя синтаксис явного переопределения.  
  
```  
  
// explicit_override_2.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
interface struct I2 {  
   virtual void f();  
};  
  
ref struct X : public I1, I2 {  
   virtual void f() = I1::f, I2::f {  
      System::Console::WriteLine("X::f override of I1::f and I2::f");  
   }  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   I2 ^ MyI2 = gcnew X;  
   MyI -> f();  
   MyI2 -> f();  
}  
```  
  
 **Output**  
  
  **X::f override of I1::f and I2::f**  
 **X::f override of I1::f and I2::f** **Пример**  
  
 В следующем примере кода показано, как переопределение функции может иметь имя отличное от имени функции, которую она реализует.  
  
```  
// explicit_override_3.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X : public I1 {  
public:  
   virtual void g() = I1::f {  
      System::Console::WriteLine("X::g");  
   }  
};  
  
int main() {  
   I1 ^ a = gcnew X;  
   a->f();  
}  
```  
  
 **Output**  
  
  **X::g** **Пример**  
  
 В следующем примере кода показана явная реализация интерфейса, реализующая типобезопасную коллекцию.  
  
```  
// explicit_override_4.cpp  
// compile with: /clr /LD  
using namespace System;  
ref class R : ICloneable {  
   int X;  
  
   virtual Object^ C() sealed = ICloneable::Clone {  
      return this->Clone();  
   }  
  
public:  
   R() : X(0) {}  
   R(int x) : X(x) {}  
  
   virtual R^ Clone() {  
      R^ r = gcnew R;  
      r->X = this->X;  
      return r;  
   }  
};  
```  
  
## См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)