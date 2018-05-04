---
title: Назначение | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], assignment
- assignment operators [C++], overloaded
ms.assetid: d87e4f89-f8f5-42c1-9d3c-184bca9d0e15
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 66fd08215c3849bf487578b28b1824afbec14c52
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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