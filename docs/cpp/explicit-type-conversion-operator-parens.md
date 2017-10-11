---
title: "Оператор явного преобразования типа: () | Документы Microsoft"
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
- explicit data type conversion operator
- conversions [C++], explicit
- operators [C++], explicit type conversion
- data type conversion [C++], explicit
- type conversion [C++], explicit conversions
ms.assetid: 54272006-5ffb-45ed-8283-27152ab97529
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 09afbed7f5a399b9ca192ff57be1c866baf59626
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="explicit-type-conversion-operator-"></a>Оператор явного преобразования типа: ()
В C++ разрешаются явные преобразования типов с использованием синтаксиса, аналогичного синтаксису вызова функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
simple-type-name ( expression-list )  
```  
  
## <a name="remarks"></a>Примечания  
 Объект *простое имя типа* следуют *список выражений* заключены в круглые скобки конструкции объекта указанного типа, используя указанное выражение. В следующем примере показано явное преобразование типа в тип int.  
  
```  
int i = int( d );  
```  
  
 В следующем примере показан `Point` класса.  
  
## <a name="example"></a>Пример  
  
```  
// expre_Explicit_Type_Conversion_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class Point  
{  
public:  
    // Define default constructor.  
    Point() { _x = _y = 0; }  
    // Define another constructor.  
    Point( int X, int Y ) { _x = X; _y = Y; }  
  
    // Define "accessor" functions as  
    // reference types.  
    unsigned& x() { return _x; }  
    unsigned& y() { return _y; }  
    void Show()   { cout << "x = " << _x << ", "  
                         << "y = " << _y << "\n"; }  
private:  
    unsigned _x;  
    unsigned _y;  
};  
  
int main()  
{  
    Point Point1, Point2;  
  
    // Assign Point1 the explicit conversion  
    //  of ( 10, 10 ).  
    Point1 = Point( 10, 10 );  
  
    // Use x() as an l-value by assigning an explicit  
    //  conversion of 20 to type unsigned.  
    Point1.x() = unsigned( 20 );  
    Point1.Show();  
  
    // Assign Point2 the default Point object.  
    Point2 = Point();  
    Point2.Show();  
}  
```  
  
## <a name="output"></a>Вывод  
  
```  
x = 20, y = 10  
x = 0, y = 0  
```  
  
 Хотя в предыдущем примере показано явное преобразование типов с помощью констант, тот же метод применим и для выполнения таких преобразований для объектов. Это демонстрируется в следующем фрагменте кода.  
  
```  
int i = 7;  
float d;  
  
d = float( i );  
```  
  
 Явные преобразования типов также можно задавать с помощью синтаксиса приведения. Предыдущий пример, перезаписанный с использованием синтаксиса приведения, выглядит следующим образом:  
  
```  
d = (float)i;  
```  
  
 Преобразования отдельных значений в стиле приведения и в стиле функции дают одинаковые результаты. Однако в синтаксисе стиля функции можно определить несколько аргументов для преобразования. Это различие имеет важное значение для пользовательских типов. Рассмотрим класс `Point` и его преобразования.  
  
```  
struct Point  
{  
    Point( short x, short y ) { _x = x; _y = y; }  
    ...  
    short _x, _y;  
};  
...  
Point pt = Point( 3, 10 );  
```  
  
 Предыдущий пример, использующий функциональное преобразование, показано, как преобразовать два значения (одно для *x* и один для *y*) для определяемого пользователем типа `Point`.  
  
> [!CAUTION]
>  Явные преобразования типов следует использовать с осторожностью, поскольку они переопределяют встроенную проверку типов компилятора C++.  
  
 [Приведения](../cpp/cast-operator-parens.md) notation должен использоваться для преобразования в типы, у которых нет *простое имя типа* (указатель или ссылка или типов, например). Преобразование в типы, которые могут быть выражены с *простое имя типа* можно записать в любой форме. В разделе [спецификаторы типа](http://msdn.microsoft.com/en-us/34b6c737-0ef1-4470-9b77-b26e46c0bbd4) Дополнительные сведения о том, что такое *простое имя типа*.  
  
 Определение типа в приведениях недопустимо.  
  
## <a name="see-also"></a>См. также  
 [Постфиксные выражения](../cpp/postfix-expressions.md)   
 [Встроенные операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
