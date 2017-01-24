---
title: "Оператор вызова функции: () | Microsoft Docs"
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
  - "( ) - оператор вызова функции"
  - "() - оператор вызова функции"
  - "оператор вызова функции ( )"
  - "вызовы функций, функции C++"
  - "вызовы функций, оператор"
  - "функции [C++], оператор вызова функции"
  - "постфиксные операторы"
ms.assetid: 50c92e59-a4bf-415a-a6ab-d66c679ee80a
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор вызова функции: ()
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Постфиксное выражение с последующим оператором вызова функции, **\( \)**, определяет вызов функции.  
  
## Синтаксис  
  
```  
  
postfix-expression   
( [argument-expression-list ] )  
```  
  
## Заметки  
 Аргументы оператора вызова функции — ноль или более выражений, разделенных запятыми. Эти выражения являются фактическими аргументами функции.  
  
 *Постфиксное\-выражение* должно вычислять адрес функции \(например, идентификатор функции или значение указателя функции\), а *список\-выражений\-аргументов* — это список выражений \(разделенных запятыми\), значения которых \(аргументы\) передаются функции.  Аргумент *список\-выражений\-аргументов* может быть пустым.  
  
 *Постфиксное\-выражение* должно быть одного из указанных ниже типов.  
  
-   Функция, возвращающая тип `T`.  Пример объявления:  
  
    ```  
    T func( int i )  
    ```  
  
-   Указатель на функцию, возвращающую тип `T`.  Пример объявления:  
  
    ```  
    T (*func)( int i )  
    ```  
  
-   Ссылка на функцию, возвращающую тип `T`.  Пример объявления:  
  
    ```  
    T (&func)(int i)  
    ```  
  
-   Разыменование функции указателя на член, возвращающее тип `T`.  Примеры вызовов функции:  
  
    ```  
    (pObject->*pmf)();  
    (Object.*pmf)();  
    ```  
  
## Пример  
 В следующем примере вызывается функция стандартной библиотеки `strcat_s` с тремя аргументами:  
  
```  
// expre_Function_Call_Operator.cpp  
// compile with: /EHsc  
  
#include <iostream>  
#include <string>  
  
// STL name space  
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
  
  **Добро пожаловать в C\+\+**   
## Результаты вызова функции  
 Вызов функции возвращает r\-значение, если функция не объявлена как ссылочный тип.  Функции с возвращаемым ссылочным типом возвращают l\-значение и могут использоваться в левой части оператора присваивания следующим образом.  
  
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
  
 В предыдущем коде определяется класс с именем `Point`, который содержит закрытые объекты данных, представляющие координаты *x* и *y*.  Эти объекты данных необходимо изменить, а значения — извлечь.  Программа — это лишь одно из нескольких решений для такого класса. Также можно использовать функции `GetX` и `SetX` или `GetY` и `SetY`.  
  
 Функции, возвращающие типы классов, указатели на типы классов или ссылки на типы классов можно использовать как левый операнд в операторах выбора члена.  Поэтому следующий код допустим.  
  
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
  
 Функции можно вызывать рекурсивно.  Дополнительные сведения об объявлениях функций см. в разделах [Описатели функций](../misc/function-specifiers.md) и [Функции\-члены](../Topic/Member%20Functions%20\(C++\).md).  Связанные материалы см. в разделе [Программа и компоновка](../cpp/program-and-linkage-cpp.md).  
  
## См. также  
 [Постфиксные выражения](../cpp/postfix-expressions.md)   
 [Операторы C\+\+](../misc/cpp-operators.md)   
 [Операторы C\+\+, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Вызов функции](../c-language/function-call-c.md)   
 [\(NOTINBUILD\) Function Declarations](http://msdn.microsoft.com/ru-ru/3f9b4e14-60d2-47c1-acd8-4fa8fc988be7)