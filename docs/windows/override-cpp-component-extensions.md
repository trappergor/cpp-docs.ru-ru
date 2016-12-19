---
title: "override (расширения компонентов C++) | Microsoft Docs"
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
  - "override - ключевое слово [C++]"
  - "переопределение, override - ключевое слово [C++]"
ms.assetid: 34d19257-1686-4fcd-96f5-af07c70ba914
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# override (расширения компонентов C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Контекстно\-зависимое ключевое слово `override` указывает, что элемент типа переопределяет член базового класса или базового интерфейса.  
  
## Примечания  
 Ключевое слово `override` допустимо при компилировании для собственных целевых объектов \(параметр компилятора по умолчанию\), целевых объектов среды выполнения Windows \(параметр компилятора **\/ZW** \) или целевых объектов среды CLR \(параметр компилятора **\/clr** \).  
  
 Дополнительные сведения о спецификаторах переопределения см. в разделах [Спецификатор override](../cpp/override-specifier.md) и [Спецификаторы переопределения и собственные компиляции](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).  
  
 Дополнительные сведения о контекстно\-зависимых ключевых словах см. в разделе [Контекстные ключевые слова](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
## Примеры  
 **Пример**  
  
 В следующем примере кода показано, что `override` также можно использовать в собственных компиляциях.  
  
```cpp#  
// override_keyword_1.cpp  
// compile with: /c  
struct I1 {  
   virtual void f();  
};  
  
struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **Пример**  
  
 В следующем примере кода показано, что `override` можно использовать в компиляциях среды выполнения Windows.  
  
```cpp#  
// override_keyword_2.cpp  
// compile with: /ZW /c  
ref struct I1 {  
   virtual void f();  
};  
  
ref struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **Требования**  
  
 Параметр компилятора: **\/ZW**  
  
 **Пример**  
  
 В следующем примере кода показано, что `override` можно использовать в компиляциях среды CLR.  
  
```cpp#  
// override_keyword_3.cpp  
// compile with: /clr /c  
ref struct I1 {  
   virtual void f();  
};  
  
ref struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **Требования**  
  
 Параметр компилятора: **\/clr**  
  
## См. также  
 [Спецификатор override](../cpp/override-specifier.md)   
 [Спецификаторы переопределения](../windows/override-specifiers-cpp-component-extensions.md)