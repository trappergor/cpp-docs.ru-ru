---
title: "Ключевое слово auto | Microsoft Docs"
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
  - "auto"
  - "auto_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto - ключевое слово"
  - "автоматический класс хранения, auto - ключевое слово"
ms.assetid: 744a41c0-2510-4140-a1be-96257e722908
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ключевое слово auto
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ключевое слово `auto` является описателем объявления.  Однако стандарт языка C\+\+ определяет первоначальное и измененное значение данного ключевого слова.  До версии [!INCLUDE[cpp_dev10_long](../Token/cpp_dev10_long_md.md)] ключевое слово `auto` объявляло переменную в *автоматическом* классе хранения; то есть переменную с локальным временем существования.  Начиная с [!INCLUDE[cpp_dev10_long](../Token/cpp_dev10_long_md.md)] ключевое слово `auto` объявляет переменную, тип которой выводится из выражения инициализации в соответствующем объявлении.  Параметр компилятора [\/Zc:auto&#91;\-&#93;](../build/reference/zc-auto-deduce-variable-type.md) контролирует значение ключевого слова `auto`.  
  
## Синтаксис  
  
```cpp  
auto declarator ;  
auto declarator initializer;  
```  
  
## Заметки  
 Определение ключевого слова `auto` меняется в языке программирования C\+\+, но не в С.  
  
 В следующих разделах описывается ключевое слово `auto` и соответствующий параметр компилятора:  
  
-   [auto](../cpp/auto-cpp.md) описывает новое определение ключевого слова `auto`.  
  
-   [Ключевое слово auto \(спецификатор классов хранения\)](http://msdn.microsoft.com/ru-ru/c7d0cecf-393d-4058-a6e6-b39e31d9edb0) описывает исходное определение ключевого слова `auto`.  
  
-   [\/Zc:auto \(выведение типа переменной\)](../build/reference/zc-auto-deduce-variable-type.md) описывает параметр компилятора, который указывает компилятору, какое определение ключевого слова `auto` следует использовать.  
  
## См. также  
 [\(NOTINBUILD\)Storage\-Class Specifiers](http://msdn.microsoft.com/ru-ru/10b3d22d-cb40-450b-994b-08cf9a211b6c)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)