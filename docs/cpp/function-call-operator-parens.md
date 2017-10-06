---
title: "Оператор вызова функции: () | Документы Microsoft"
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
- ( ) function call operator
- function calls, C++ functions
- () function call operator
- postfix operators [C++]
- function calls, operator
- functions [C++], function-call operator
- function call operator ()
ms.assetid: 50c92e59-a4bf-415a-a6ab-d66c679ee80a
caps.latest.revision: 14
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
ms.openlocfilehash: bcd44b1c33488d4bbe4dac8bfe541dfa04f4709a
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="function-call-operator-"></a>Оператор вызова функции: ()
Постфиксное выражение с последующим оператором вызова функции, **()**, определяет вызов функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
postfix-expression   
( [argument-expression-list ] )  
```  
  
## <a name="remarks"></a>Примечания  
 Аргументы оператора вызова функции — ноль или более выражений, разделенных запятыми. Эти выражения являются фактическими аргументами функции.  
  
 *Постфиксное выражение* должны иметь адрес функции (например, идентификатор функции или значение указателя функции) и *список выражений аргументов* — список выражений (разделенных через запятую), значения которых (аргументы) передаются функции. Аргумент *argument-expression-list* может быть пустым.  
  
 *Постфиксное выражение* должны иметь один из этих типов:  
  
-   Функция, возвращающая тип `T`. Пример объявления:  
  
    ```  
    T func( int i )  
    ```  
  
-   Указатель на функцию, возвращающую тип `T`. Пример объявления:  
  
    ```  
    T (*func)( int i )  
    ```  
  
-   Ссылка на функцию, возвращающую тип `T`. Пример объявления:  
  
    ```  
    T (&func)(int i)  
    ```  
  
-   Разыменование функции указателя на член, возвращающее тип `T`. Примеры вызовов функции:  
  
    ```  
    (pObject->*pmf)();  
    (Object.*pmf)();  
    ```  
  
## <a name="example"></a>Пример  
 В следующем примере вызывается функция стандартной библиотеки `strcat_s` с тремя аргументами:  
  
```  
// expre_Function_Call_Operator.cpp  
// compile with: /EHsc  
  
#include <iostream>  
#include <string>  
  
// C++ Standard Library name space  
using namespace std;  
  
int main()  
{  
    enum  
    {  
        sizeOfBuffer = 20  
    };  
  
    char s1[ sizeOfBuffer ] = "Welcome to ";  
    char s2[ ] = "C++";  
  
    strcat_s( s1, sizeOfBuffer, s2 );  
  
    cout << s1 << endl;  
}  
```  
  
```Output  
Welcome to C++  
```  
  
## <a name="function-call-results"></a>Результаты вызова функции  
 Вызов функции возвращает r-значение, если функция не объявлена как ссылочный тип. Функции с ссылочным типом возвращаемого значения возвращают l-значение и могут использоваться в левой части оператора присваивания следующим образом.  
  
```  
// expre_Function_Call_Results.cpp  
// compile with: /EHsc  
#include <iostream>  
class Point  
{  
public:  
    // Define "accessor" functions as  
    // reference types.  
    unsigned& x() { return _x; }  
    unsigned& y() { return _y; }  
private:  
    unsigned _x;  
    unsigned _y;  
};  
  
using namespace std;  
int main()  
{  
    Point ThePoint;  
  
    ThePoint.x() = 7;           // Use x() as an l-value.  
    unsigned y = ThePoint.y();  // Use y() as an r-value.  
  
    // Use x() and y() as r-values.  
    cout << "x = " << ThePoint.x() << "\n"  
         << "y = " << ThePoint.y() << "\n";  
}  
```  
  
 В предыдущем коде определяется класс с именем `Point`, который содержит закрытые объекты данных, представляющего *x* и *y* координаты. Эти объекты данных необходимо изменить, а значения — извлечь. Программа — это лишь одно из нескольких решений для такого класса. Также можно использовать функции `GetX` и `SetX` или `GetY` и `SetY`.  
  
 Функции, возвращающие типы классов, указатели на типы классов или ссылки на типы классов можно использовать как левый операнд в операторах выбора члена. Поэтому следующий код допустим.  
  
```  
// expre_Function_Results2.cpp  
class A {  
public:  
   A() {}  
   A(int i) {}  
   int SetA( int i ) {  
      return (I = i);  
   }  
  
   int GetA() {  
      return I;  
   }  
  
private:  
   int I;  
};  
  
A func1() {  
   A a = 0;  
   return a;  
}  
  
A* func2() {  
   A *a = new A();  
   return a;  
}  
  
A& func3() {  
   A *a = new A();  
   A &b = *a;  
   return b;  
}  
  
int main() {  
   int iResult = func1().GetA();  
   func2()->SetA( 3 );  
   func3().SetA( 7 );  
}  
```  
  
 Функции можно вызывать рекурсивно. Дополнительные сведения об объявлениях функций см. в разделе [функции](functions-cpp.md). Связанные материалы находится в [программа и компоновка](../cpp/program-and-linkage-cpp.md).  
  
## <a name="see-also"></a>См. также  
 [Постфиксные выражения](../cpp/postfix-expressions.md)   
 [Встроенный C++ операторы, приоритет и ассоциативность операторов](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Вызов функции](../c-language/function-call-c.md)   

