---
title: "Назначение | Microsoft Docs"
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
  - "операторы присваивания, перегруженные"
  - "операторы [C++], присвоение"
ms.assetid: d87e4f89-f8f5-42c1-9d3c-184bca9d0e15
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Назначение
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Оператор присваивания \(**\=**\) является, строго говоря, бинарным оператором.  Его объявление идентично объявлению любого другого бинарного оператора, со следующими исключениями:  
  
-   Он должен быть нестатической функцией\-членом.  Никакой оператор `operator=` не может быть объявлен как функция, не являющаяся членом.  
  
-   Он не наследуется производными классами.  
  
-   Компилятор может создавать для типов классов функции `operator=` по умолчанию, если они не существуют. \(Дополнительные сведения о функциях `operator=` по умолчанию см. в разделе [Почленное присваивание и инициализация](http://msdn.microsoft.com/ru-ru/94048213-8b49-4416-8069-b1b7a6f271f9).\)  
  
 В следующем примере показано, как объявить оператор присваивания:  
  
```  
// assignment.cpp  
class Point  
{  
public:  
   Point &operator=( Point & );  // Right side is the argument.  
   int _x, _y;  
};  
  
// Define assignment operator.  
Point &Point::operator=( Point &ptRHS )  
{  
   _x = ptRHS._x;  
   _y = ptRHS._y;  
  
   return *this;  // Assignment operator returns left side.  
}  
  
int main()  
{  
}  
```  
  
 Обратите внимание, что указанный аргумент является правой частью выражения.  Оператор возвращает объект для сохранения поведения оператора присваивания, который после завершения присваивания возвращает значение левой части.  Это позволяет писать операторы следующего вида:  
  
```  
pt1 = pt2 = pt3;  
```  
  
## См. также  
 [Перегрузка операторов](../cpp/operator-overloading.md)