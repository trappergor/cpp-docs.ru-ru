---
title: "abstract (расширения компонентов C++) | Microsoft Docs"
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
  - "abstract"
  - "abstract_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "abstract - ключевое слово [C++]"
ms.assetid: cbae3408-0378-4ac8-b70d-c016b381a6d5
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# abstract (расширения компонентов C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ключевое слово `abstract` объявляет один из следующих объектов.  
  
-   Тип можно использовать в качестве базового типа, но экземпляр самого тип не может быть создан.  
  
-   Функция\-член типа может определяться только в производном типе.  
  
## Все платформы  
 **Синтаксис**  
  
```  
  
class-declaration class-identifier abstract {}  
virtual return-type member-function-identifier() abstract ;  
  
```  
  
 **Примечания**  
  
 В первом примере синтаксиса объявляется абстрактный класс.  Компонент *объявления класса* может быть либо собственным объявлением C\+\+ \(`class` или `struct`\), либо объявлением расширения C\+\+ \(`ref class` или `ref struct`\), если указан параметр компилятора **\/ZW** или **\/clr**.  
  
 Во втором примере синтаксиса объявляется абстрактная виртуальная функция\-член.  Объявление функции абстрактной — то же, что и объявление ее чистой виртуальной функцией.  Объявление функции\-члена абстрактной также приводит к тому, что включающий класс объявляется как абстрактный.  
  
 Ключевое слово `abstract` поддерживается в машинном коде и в коде платформы, то есть он может компилироваться как с параметром компилятора **\/ZW** или **\/clr**, так и без него.  
  
 Во время компиляции можно определить, является ли тип абстрактным, с помощью признака типа `__is_abstract(``type``)`.  Дополнительные сведения см. в разделе [Поддержка характеристик типов компилятором](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 Ключевое слово `abstract` является контекстно\-зависимым описателем переопределения.  Дополнительные сведения о контекстно\-зависимых ключевых словах см. в разделе [Контекстные ключевые слова](../windows/context-sensitive-keywords-cpp-component-extensions.md).  Дополнительные сведения об описателях переопределения см. в разделе [Практическое руководство. Объявление описателей переопределения в компиляциях машинного кода](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 Дополнительные сведения см. в разделе [Классы и структуры ссылки](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx).  
  
### Требования  
 Параметр компилятора: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
  
### Требования  
 Параметр компилятора: **\/clr**  
  
### Примеры  
 **Пример**  
  
 В следующем примере кода возникает ошибка, поскольку класс `X` помечен как `abstract`.  
  
```  
// abstract_keyword.cpp  
// compile with: /clr  
ref class X abstract {  
public:  
   virtual void f() {}  
};  
  
int main() {  
   X ^ MyX = gcnew X;   // C3622  
}  
```  
  
 **Пример**  
  
 В следующем примере кода возникает ошибка, поскольку он создает экземпляр собственного класса, помеченного как `abstract`.  Эта ошибка будет возникать как с параметром компилятора **\/clr**, так и без него.  
  
```  
// abstract_keyword_2.cpp  
class X abstract {  
public:  
   virtual void f() {}  
};  
  
int main() {  
   X * MyX = new X; // C3622: 'X': a class declared as 'abstract'  
                    // cannot be instantiated. See declaration of 'X'}  
  
```  
  
 **Пример**  
  
 В следующем примере кода возникает ошибка, поскольку функция `f` включает определение, но помечена как `abstract`.  Последняя инструкция в примере показывает, что объявление абстрактной виртуальной функции эквивалентно объявлению чистой виртуальной функции.  
  
```  
// abstract_keyword_3.cpp  
// compile with: /clr  
ref class X {  
public:  
   virtual void f() abstract {}   // C3634  
   virtual void g() = 0 {}   // C3634  
};  
```  
  
## См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)