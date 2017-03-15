---
title: "Явная специализация шаблонов функций | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "объявление функций, специализация шаблона функций"
  - "явная специализация шаблонов функций"
  - "шаблоны функций, специализация"
  - "переопределение, функции"
  - "специализация шаблонов функций"
ms.assetid: eb0fcb73-eaed-42a1-9b83-14b055a34bf8
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Явная специализация шаблонов функций
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Используя шаблон функции, можно указать особое поведение для определенного типа, предоставив явную специализацию \(переопределение\) шаблона функции для этого типа.  Например:  
  
```  
template<> void MySwap(double a, double b);  
```  
  
 Это объявление позволяет определить другую функцию для переменных **double**.  Как и в случае функций, не являющихся шаблоном, применяются стандартные преобразования типов \(например, преобразование типа **float** в **double**\).  
  
## Пример  
  
```  
// explicit_specialization.cpp  
template<class T> void f(T t)  
{  
};  
  
// Explicit specialization of f with 'char' with the  
// template argument explicitly specified:  
//  
template<> void f<char>(char c)  
{  
}  
  
// Explicit specialization of f with 'double' with the  
// template argument deduced:  
//  
template<> void f(double d)  
{  
}  
int main()  
{  
}  
```  
  
## См. также  
 [Шаблоны функций](../cpp/function-templates.md)