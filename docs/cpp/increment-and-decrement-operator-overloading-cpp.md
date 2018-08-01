---
title: Операторов увеличения и уменьшения перегрузка (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- increment operators [C++]
- increment operators [C++], types of
- decrement operators [C++]
- decrement operators [C++], types of
ms.assetid: 5423c6ce-3999-4a77-92f6-ad540add1b1d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b546e58b8a761660386c568c533ee2930871491
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39403876"
---
# <a name="increment-and-decrement-operator-overloading-c"></a>Перегрузка операторов увеличения и уменьшения (C++)
Операторы инкремента и декремента относятся к особой категории, поскольку имеется два варианта каждого из них:  
  
-   преинкрементный и постинкрементный операторы;  
  
-   предекрементный и постдекрементный операторы.  
  
 При написании функций перегруженных операторов полезно реализовать отдельные версии для префиксной и постфиксной форм этих операторов. Для различения двух, наблюдается следующее правило: префиксная форма оператора объявляется точно так же, как любой другой унарный оператор; в постфиксной форме принимается дополнительный аргумент типа **int**.  
  
> [!NOTE]
>  При задании перегруженного оператора для постфиксной формы оператора инкремента или декремента, дополнительный аргумент должен иметь тип **int**; указании любого другого типа приводит к ошибке.  
  
 В следующем примере показано определение операторов префиксных и постфиксных инкремента и декремента для класса `Point`.  
  
```cpp  
// increment_and_decrement1.cpp  
class Point  
{  
public:  
   // Declare prefix and postfix increment operators.  
   Point& operator++();       // Prefix increment operator.  
   Point operator++(int);     // Postfix increment operator.  
  
   // Declare prefix and postfix decrement operators.  
   Point& operator--();       // Prefix decrement operator.  
   Point operator--(int);     // Postfix decrement operator.  
  
   // Define default constructor.  
   Point() { _x = _y = 0; }  
  
   // Define accessor functions.  
   int x() { return _x; }  
   int y() { return _y; }  
private:  
   int _x, _y;  
};  
  
// Define prefix increment operator.  
Point& Point::operator++()  
{  
   _x++;  
   _y++;  
   return *this;  
}  
  
// Define postfix increment operator.  
Point Point::operator++(int)  
{  
   Point temp = *this;  
   ++*this;  
   return temp;  
}  
  
// Define prefix decrement operator.  
Point& Point::operator--()  
{  
   _x--;  
   _y--;  
   return *this;  
}  
  
// Define postfix decrement operator.  
Point Point::operator--(int)  
{  
   Point temp = *this;  
   --*this;  
   return temp;  
}  
int main()  
{  
}  
```  
  
 Те же операторы можно определить в области видимости файла (глобально) с помощью следующих заголовков функций:  
  
```cpp  
friend Point& operator++( Point& )      // Prefix increment  
friend Point& operator++( Point&, int ) // Postfix increment  
friend Point& operator--( Point& )      // Prefix decrement  
friend Point& operator--( Point&, int ) // Postfix decrement  
```  
  
 Аргумент типа **int** , обозначающий постфиксную форму приращения или оператор декремента не часто используется для передачи аргументов. Он обычно содержит значение 0. Однако его можно использовать следующим образом:  
  
```cpp  
// increment_and_decrement2.cpp  
class Int  
{  
public:  
    Int &operator++( int n );  
private:  
    int _i;  
};  
  
Int& Int::operator++( int n )  
{  
    if( n != 0 )    // Handle case where an argument is passed.  
        _i += n;  
    else  
        _i++;       // Handle case where no argument is passed.  
    return *this;  
}  
int main()  
{  
   Int i;  
   i.operator++( 25 ); // Increment by 25.  
}  
```  
  
 Для передачи этих значений с помощью операторов инкремента и декремента не существует иного синтаксиса, кроме явного вызова, как показано в предыдущем примере. Более простой способ реализации этой функции — перегрузка оператора сложения и присваивания (**+=**).  
  
## <a name="see-also"></a>См. также  
 [Перегрузка операторов](../cpp/operator-overloading.md)