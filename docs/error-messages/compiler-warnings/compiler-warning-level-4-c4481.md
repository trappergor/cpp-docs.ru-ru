---
title: "Предупреждение компилятора (уровень 4) C4481 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4481"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4481"
ms.assetid: 7bfd4e0c-b452-4e6c-b7c4-ac5cc93fe4ea
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 4) C4481
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

использовано нестандартное расширение: спецификатор переопределения "ключевое слово"  
  
 Используется ключевое слово, не соответствующее стандартам C\+\+, например один из спецификаторов переопределения, которые также могут использоваться с параметром \/clr.  Дополнительные сведения см. в следующих разделах:  
  
-   [\/clr \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Спецификаторы переопределения](../../windows/override-specifiers-cpp-component-extensions.md)  
  
## Пример  
 В следующем примере возникает предупреждение C4481.  
  
```  
// C4481.cpp  
// compile with: /W4 /c  
class B {  
   virtual void f(unsigned);  
};  
  
class C : B {  
   void f(unsigned) override;   // C4481  
   void f2(unsigned);  
};  
```