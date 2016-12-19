---
title: "void (C++) | Microsoft Docs"
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
  - "void"
  - "void_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "функции [C++], void"
  - "указатели, void"
  - "void - ключевое слово [C++]"
ms.assetid: d203edba-38e6-4056-8b89-011437351057
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# void (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Если ключевое слово `void` указывает возвращаемый тип функции, оно означает, что данная функция не возвращает никакого значения.  Если оно используется для списка параметров функции, оно означает, что функция не принимает никаких параметров.  Если оно используется в объявлении указателя, оно означает, что указатель является "универсальным".  
  
 Если указатель имеет тип **void \***, он может указывать на любую переменную, объявленную без указания ключевого слова **const** или `volatile`.  Указатель с ключевым словом void не может быть разыменован, кроме как путем приведения к другому типу.  Указатель с ключевым словом void может быть преобразован в любой другой тип указателя на данные.  
  
 В C\+\+ указатель с ключевым словом void может указывать на функцию, но не на класса.  
  
 Объявить переменную типа void невозможно.  
  
## Пример  
  
```  
// void.cpp  
void vobject;   // C2182  
void *pv;   // okay  
int *pint; int i;  
int main() {  
   pv = &i;  
   // Cast optional in C required in C++  
   pint = (int *)pv;  
}   
```  
  
## См. также  
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)   
 [Указатели на тип void](../misc/pointers-to-type-void.md)   
 [Фундаментальные типы](../cpp/fundamental-types-cpp.md)