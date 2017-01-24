---
title: "sealed (расширения компонентов C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "sealed_cpp"
  - "sealed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sealed - ключевое слово [C++]"
ms.assetid: 3d0d688a-41aa-45f5-a25a-65c44206521e
caps.latest.revision: 26
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# sealed (расширения компонентов C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`sealed` — это контекстно\-зависимое ключевое слово для ссылочных классов, которое означает, что виртуальный член нельзя переопределить или что тип не может использоваться в качестве базового типа.  
  
> [!NOTE]
>  Стандарт языка ISO C\+\+11 имеет ключевое слово [final](../cpp/final-specifier.md), которое поддерживается в Visual Studio.  Используйте `final` в стандартных классов, а `sealed` в ссылочных классах.  
  
## Все среды выполнения  
 **Синтаксис**  
  
```  
  
ref class identifier sealed {...};  
virtual return-type identifier() sealed {...};  
  
```  
  
 **Параметры**  
  
 *identifier*  
 Имя функции или класса.  
  
 *return\-type*  
 Тип, который возвращается функцией.  
  
 **Примечания**  
  
 В первом примере синтаксиса запечатан \(sealed\) класс.  Во втором примере запечатана виртуальная функция.  
  
 Ключевое слово `sealed` является допустимым при компиляции в машинный код, а также для [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] и среды CLR.  Дополнительные сведения см. в разделе [Спецификаторы переопределения и  компиляция в машинный код](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).  
  
 Во время компиляции можно определить, запечатан ли тип, используя характеристику типа `__is_sealed (``type``)`.  Дополнительные сведения см. в разделе [Поддержка характеристик типов компилятором](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 `sealed` — контекстно\-зависимое ключевое слово.  Дополнительные сведения см. в разделе [Контекстные ключевые слова](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 См. [Ссылочные классы и структуры](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx).  
  
### Требования  
 Параметр компилятора: **\/ZW**  
  
## Среда CLR  
 \(Отсутствуют комментарии для этой функции языка, которая применяется только в среде CLR\).  
  
### Требования  
 Параметр компилятора: **\/clr**  
  
### Примеры  
 В следующем примере кода показано влияние `sealed` на виртуальный член.  
  
```cpp  
// sealed_keyword.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
   virtual void g();  
};  
  
ref class X : I1 {  
public:  
   virtual void f() {  
      System::Console::WriteLine("X::f override of I1::f");  
   }  
  
   virtual void g() sealed {  
      System::Console::WriteLine("X::f override of I1::g");  
   }  
};  
  
ref class Y : public X {  
public:  
   virtual void f() override {  
      System::Console::WriteLine("Y::f override of I1::f");  
   }  
  
   /*  
   // the following override generates a compiler error  
   virtual void g() override {  
      System::Console::WriteLine("Y::g override of I1::g");  
   }    
   */  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   MyI -> f();  
   MyI -> g();  
  
   I1 ^ MyI2 = gcnew Y;  
   MyI2 -> f();  
}  
```  
  
 **Вывод**  
  
  **X::f override of I1::f**  
 **X::f override of I1::g**  
 **Y::f override of I1::f** В следующем примере кода показано, как пометить класс запечатанным.  
  
```cpp  
// sealed_keyword_2.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X sealed : I1 {  
public:  
   virtual void f() override {}  
};  
  
ref class Y : public X {   // C3246 base class X is sealed  
public:  
   virtual void f() override {}  
};  
```  
  
## См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)