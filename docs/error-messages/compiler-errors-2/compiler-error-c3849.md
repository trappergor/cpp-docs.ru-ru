---
title: "Ошибка компилятора C3849 | Microsoft Docs"
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
  - "C3849"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3849"
ms.assetid: 5347140e-1a81-4841-98c0-b63d98264b64
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3849
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

при вызове в стиле функции выражения типа "тип" будут потеряны квалификаторы const и volatile для всех доступных перегрузок операторов  
  
 Переменная с указанным типом квалификатора const и volatile может только вызывать функции\-члены, определенные с помощью тех же или больших квалификаторов const и volatile.  
  
 Чтобы устранить данную ошибку, необходимо предоставить соответствующую функцию\-член.  Невозможно выполнить преобразование для объекта, квалифицированного как const или volatile, если преобразование является причиной потери квалификации.  При преобразовании допустимо получать квалификаторы, но не утрачивать их.  
  
 Следующий пример демонстрирует причины возникновения ошибки C3849:  
  
```  
// C3849.cpp  
void glbFunc3(int i, char c)  
{  
   i;  
}  
typedef void (* pFunc3)(int, char);  
  
void glbFunc2(int i)  
{  
   i;  
}  
  
typedef void (* pFunc2)(int);  
  
void glbFunc1()  
{  
}  
typedef void (* pFunc1)();  
  
struct S4  
{  
   operator ()(int i)  
   {  
      i;  
   }  
  
   operator pFunc1() const  
   {  
      return &glbFunc1;  
   }  
  
   operator pFunc2() volatile  
   {  
      return &glbFunc2;  
   }  
  
   operator pFunc3()  
   {  
      return &glbFunc3;  
   }  
  
   // operator pFunc1() const volatile  
   // {  
   //    return &glbFunc1;  
   // }  
};  
  
int main()  
{  
   // Cannot call any of the 4 overloads of "operator ()(.....)" and   
   // "operator pFunc()" because none is declared as "const volatile"  
   const volatile S4 s4;  // can only call cv member functions of S4  
   s4();   // C3849 to resolve, uncomment member function  
}  
```