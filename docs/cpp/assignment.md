---
title: "Назначение | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], assignment
- assignment operators, overloaded
ms.assetid: d87e4f89-f8f5-42c1-9d3c-184bca9d0e15
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: c80a11e38225a8ed4fa424bbd3009e5701848cbd
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="assignment"></a>Назначение
Оператор присваивания (**=**) является, строго говоря, бинарным оператором. Его объявление идентично объявлению любого другого бинарного оператора, со следующими исключениями:  
  
-   Он должен быть нестатической функцией-членом. Никакой оператор `operator=` не может быть объявлен как функция, не являющаяся членом.  
  
-   Он не наследуется производными классами.  
  
-   Компилятор может создавать для типов классов функции `operator=` по умолчанию, если они не существуют. (Дополнительные сведения о умолчанию `operator=` функции, в разделе [Поэлементное присваивание и инициализация](http://msdn.microsoft.com/en-us/94048213-8b49-4416-8069-b1b7a6f271f9).)  
  
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
  
 Обратите внимание, что указанный аргумент является правой частью выражения. Оператор возвращает объект для сохранения поведения оператора присваивания, который после завершения присваивания возвращает значение левой части. Это позволяет писать операторы следующего вида:  
  
```  
pt1 = pt2 = pt3;  
```  
  
## <a name="see-also"></a>См. также  
 [Перегрузка операторов](../cpp/operator-overloading.md)
