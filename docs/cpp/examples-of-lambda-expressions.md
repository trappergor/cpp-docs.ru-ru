---
title: "Примеры лямбда-выражений | Microsoft Docs"
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
  - "лямбда-выражения [C++], примеры"
ms.assetid: 52506b15-0771-4190-a966-2f302049ca86
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# Примеры лямбда-выражений
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В данной статье приводится описание методов использования лямбда\-выражений в программах.  Общие сведения о лямбда\-выражениях см. в разделе [Лямбда\-выражения](../cpp/lambda-expressions-in-cpp.md).  Дополнительные сведения о структуре лямбда\-выражений см. в разделе [Синтаксис лямбда\-выражений](../cpp/lambda-expression-syntax.md).  
  
##  <a name="top"></a> Содержание этой статьи  
 [Объявление лямбда-выражений](#declaringLambdaExpressions)  
  
 [Вызов лямбда-выражений](#callingLambdaExpressions)  
  
 [Вложение лямбда-выражений](#nestingLambdaExpressions)  
  
 [Лямбда-функции высшего порядка](#higherOrderLambdaExpressions)  
  
 [Использование лямбда-выражения в функции](#methodLambdaExpressions)  
  
 [Использование лямбда-выражения с шаблонами](#templateLambdaExpressions)  
  
 [Обработка исключений](#ehLambdaExpressions)  
  
 [Использование лямбда-выражений с управляемыми типами (C++/CLI)](#managedLambdaExpressions)  
  
##  <a name="declaringLambdaExpressions"></a> Объявление лямбда\-выражений  
  
### Пример 1  
 Поскольку лямбда\-выражение имеет тип, можно присвоить его переменной `auto` или объекту [функция](../standard-library/function-class.md), как показано ниже:  
  
### Код  
  
```cpp  
// declaring_lambda_expressions1.cpp  
// compile with: /EHsc /W4  
#include <functional>  
#include <iostream>  
  
int main()  
{  
  
    using namespace std;  
  
    // Assign the lambda expression that adds two numbers to an auto variable.  
    auto f1 = [](int x, int y) { return x + y; };  
  
    cout << f1(2, 3) << endl;  
  
    // Assign the same lambda expression to a function object.  
    function<int(int, int)> f2 = [](int x, int y) { return x + y; };  
  
    cout << f2(3, 4) << endl;  
}  
```  
  
### Вывод  
  **5**  
**7**   
### Примечания  
 Дополнительные сведения см. в разделах [auto](../cpp/auto-cpp.md), [Класс function](../standard-library/function-class.md) и [Вызов функции](../Topic/Function%20Call%20\(C++\).md).  
  
 Хотя лямбда\-выражения чаще всего объявляются в теле функции, можно объявлять их в любом месте, где можно инициализировать переменные.  
  
### Пример 2  
 Компилятор Visual C\+\+ привязывает лямбда\-выражение к его захваченным переменным, когда выражение объявляется, а не при вызове выражения.  В следующем примере содержится лямбда\-выражение, которое фиксирует локальную переменную `i` по значению, а локальную переменную `j` — по ссылке.  Поскольку лямбда\-выражение захватывает `i` по значению, переопределение `i` далее в программе не влияет на результат выражения.  Однако, поскольку лямбда\-выражение захватывает `j` по ссылке, переопределение `j` влияет на результат выражения.  
  
### Код  
  
```cpp  
// declaring_lambda_expressions2.cpp  
// compile with: /EHsc /W4  
#include <functional>  
#include <iostream>  
  
int main()  
{  
   using namespace std;  
  
   int i = 3;  
   int j = 5;  
  
   // The following lambda expression captures i by value and  
   // j by reference.  
   function<int (void)> f = [i, &j] { return i + j; };  
  
   // Change the values of i and j.  
   i = 22;  
   j = 44;  
  
   // Call f and print its result.  
   cout << f() << endl;  
}  
```  
  
### Вывод  
  **47** \[[Содержание этой статьи](#top)\]  
  
##  <a name="callingLambdaExpressions"></a> Вызов лямбда\-выражений  
 Можно вызывать лямбда\-выражение сразу же, как показано в следующем фрагменте кода.  Второй фрагмент показывает, как передавать лямбда\-выражение в качестве аргумента алгоритмам библиотеки стандартных шаблонов \(STL\), например `find_if`.  
  
### Пример 1  
 В этом примере объявляется лямбда\-выражение, которое возвращает сумму двух целых чисел и сразу же вызывает выражение с аргументами `5` и `4`.  
  
### Код  
  
```cpp  
// calling_lambda_expressions1.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main()  
{  
   using namespace std;  
   int n = [] (int x, int y) { return x + y; }(5, 4);  
   cout << n << endl;  
}  
```  
  
### Вывод  
  **9**   
### Пример 2  
 В этом примере лямбда\-выражение передается в качестве аргумента функции `find_if`.  Лямбда\-выражение возвращает значение `true`, если его параметром является четное число.  
  
### Код  
  
```cpp  
// calling_lambda_expressions2.cpp  
// compile with: /EHsc /W4  
#include <list>  
#include <algorithm>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
  
    // Create a list of integers with a few initial elements.  
    list<int> numbers;  
    numbers.push_back(13);  
    numbers.push_back(17);  
    numbers.push_back(42);  
    numbers.push_back(46);  
    numbers.push_back(99);  
  
    // Use the find_if function and a lambda expression to find the   
    // first even number in the list.  
    const list<int>::const_iterator result =   
        find_if(numbers.begin(), numbers.end(),[](int n) { return (n % 2) == 0; });  
  
    // Print the result.  
    if (result != numbers.end()) {  
        cout << "The first even number in the list is " << *result << "." << endl;  
    } else {  
        cout << "The list contains no even numbers." << endl;  
    }  
}  
```  
  
### Вывод  
  **The first even number in the list is 42.**   
### Примечания  
 Дополнительные сведения о функции `find_if` см. в разделе [find\_if](../Topic/find_if.md).  Дополнительные сведения о функциях STL, реализующих типичные алгоритмы, см. в разделе [\<algorithm\>](../standard-library/algorithm.md).  
  
 \[[Содержание этой статьи](#top)\]  
  
##  <a name="nestingLambdaExpressions"></a> Вложение лямбда\-выражений  
  
### Пример  
 Можно вложить одно лямбда\-выражение в другое, как показано в следующем примере.  Внутреннее лямбда\-выражение умножает его аргумент на 2 и возвращает результат.  Внешнее лямбда\-выражение вызывает внутреннее лямбда\-выражение с использованием его аргумента и добавляет к результату 3.  
  
### Код  
  
```cpp  
// nesting_lambda_expressions.cpp  
// compile with: /EHsc /W4  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
  
    // The following lambda expression contains a nested lambda  
    // expression.  
    int timestwoplusthree = [](int x) { return [](int y) { return y * 2; }(x) + 3; }(5);  
  
    // Print the result.  
    cout << timestwoplusthree << endl;  
}  
  
```  
  
### Вывод  
  **13**   
### Примечания  
 В этом примере значение параметра `[](int y) { return y * 2; }` является вложенным лямбда\-выражением.  
  
 \[[Содержание этой статьи](#top)\]  
  
##  <a name="higherOrderLambdaExpressions"></a> Лямбда\-функции высшего порядка  
  
### Пример  
 Многие языки программирования поддерживают понятие *функции высшего порядка.* Функция высшего порядка представляет собой лямбда\-выражение, которое принимает другое лямбда\-выражение в качестве аргумента или возвращает лямбда\-выражение.  Можно использовать класс [функция](../standard-library/function-class.md), чтобы лямбда\-выражение C\+\+ могло функционировать как функция высшего порядка.  В следующем примере показано лямбда\-выражение, которое возвращает объект `function`, и лямбда\-выражение, которое принимает объект `function` в качестве аргумента.  
  
### Код  
  
```cpp  
// higher_order_lambda_expression.cpp  
// compile with: /EHsc /W4  
#include <iostream>  
#include <functional>  
  
int main()  
{  
    using namespace std;  
  
    // The following code declares a lambda expression that returns   
    // another lambda expression that adds two numbers.   
    // The returned lambda expression captures parameter x by value.  
    auto addtwointegers = [](int x) -> function<int(int)> {   
        return [=](int y) { return x + y; };   
    };  
  
    // The following code declares a lambda expression that takes another  
    // lambda expression as its argument.  
    // The lambda expression applies the argument z to the function f  
    // and multiplies by 2.  
    auto higherorder = [](const function<int(int)>& f, int z) {   
        return f(z) * 2;   
    };  
  
    // Call the lambda expression that is bound to higherorder.   
    auto answer = higherorder(addtwointegers(7), 8);  
  
    // Print the result, which is (7+8)*2.  
    cout << answer << endl;  
}  
  
```  
  
### Вывод  
  **30** \[[Содержание этой статьи](#top)\]  
  
##  <a name="methodLambdaExpressions"></a> Использование лямбда\-выражения в функции  
  
### Пример  
 Лямбда\-выражения можно использовать в теле функции.  Лямбда\-выражение может получать доступ к любой функции или данным\-членам, которые способна использовать включающая функция.  Можно явно или неявно захватывать указатель `this` для предоставления доступа к функциям и данным\-членам включающего класса.  
  
 Можно явно использовать указатель `this` в функции, как показано ниже:  
  
```cpp  
void ApplyScale(const vector<int>& v) const  
{  
   for_each(v.begin(), v.end(),   
      [this](int n) { cout << n * _scale << endl; });  
}  
```  
  
 Можно также захватывать указатель `this` неявно:  
  
```  
void ApplyScale(const vector<int>& v) const  
{  
   for_each(v.begin(), v.end(),   
      [=](int n) { cout << n * _scale << endl; });  
}  
```  
  
 В следующем примере показан класс `Scale`, который инкапсулирует значение масштаба.  
  
```cpp  
// function_lambda_expression.cpp  
// compile with: /EHsc /W4  
#include <algorithm>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
class Scale  
{  
public:  
    // The constructor.  
    explicit Scale(int scale) : _scale(scale) {}  
  
    // Prints the product of each element in a vector object   
    // and the scale value to the console.  
    void ApplyScale(const vector<int>& v) const  
    {  
        for_each(v.begin(), v.end(), [=](int n) { cout << n * _scale << endl; });  
    }  
  
private:  
    int _scale;  
};  
  
int main()  
{  
    vector<int> values;  
    values.push_back(1);  
    values.push_back(2);  
    values.push_back(3);  
    values.push_back(4);  
  
    // Create a Scale object that scales elements by 3 and apply  
    // it to the vector object. Does not modify the vector.  
    Scale s(3);  
    s.ApplyScale(values);  
}  
  
```  
  
### Вывод  
  **3**  
**6**  
**9**  
**12**   
### Примечания  
 Функция `ApplyScale` использует лямбда\-выражение для выведения произведения масштаба на каждый элемент объекта `vector`.  Лямбда\-выражение неявно захватывает `this`, чтобы получить доступ к члену `_scale`.  
  
 \[[Содержание этой статьи](#top)\]  
  
##  <a name="templateLambdaExpressions"></a> Использование лямбда\-выражения с шаблонами  
  
### Пример  
 Поскольку лямбда\-выражения имеют тип, их можно использовать с шаблонами C\+\+.  В следующем примере показаны функции `negate_all` и `print_all`.  Функция `negate_all` применяет унарный `operator-` к каждому элементу в объекте `vector`.  Функция `print_all` печатает каждый элемент в объекте `vector` в консоли.  
  
### Код  
  
```cpp  
// template_lambda_expression.cpp  
// compile with: /EHsc  
#include <vector>  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
  
// Negates each element in the vector object. Assumes signed data type.  
template <typename T>  
void negate_all(vector<T>& v)  
{  
    for_each(v.begin(), v.end(), [](T& n) { n = -n; });  
}  
  
// Prints to the console each element in the vector object.  
template <typename T>  
void print_all(const vector<T>& v)  
{  
    for_each(v.begin(), v.end(), [](const T& n) { cout << n << endl; });  
}  
  
int main()  
{  
    // Create a vector of signed integers with a few elements.  
    vector<int> v;  
    v.push_back(34);  
    v.push_back(-43);  
    v.push_back(56);  
  
    print_all(v);  
    negate_all(v);  
    cout << "After negate_all():" << endl;  
    print_all(v);  
}  
  
```  
  
### Вывод  
  **34**  
**\-43**  
**56**  
**After negate\_all\(\):**  
**\-34**  
**43**  
**\-56**   
### Примечания  
 Дополнительные сведения о шаблонах C\+\+ см. в разделе [Шаблоны](../Topic/Templates%20\(C++\).md).  
  
 \[[Содержание этой статьи](#top)\]  
  
##  <a name="ehLambdaExpressions"></a> Обработка исключений  
  
### Пример  
 Тело лямбда\-выражения выполняет правила как для структурированной обработки исключений \(SEH\), так и для обработки исключений C\+\+.  Можно обработать возникшее исключение в теле лямбда\-выражения или перенести обработку исключения во включающий фрагмент.  В следующем примере функция `for_each` и лямбда\-выражение используются для заполнения объекта `vector` значениями другого.  Здесь используется блок `try`\/`catch` для обработки недопустимого доступа к первому вектору.  
  
### Код  
  
```cpp  
// eh_lambda_expression.cpp  
// compile with: /EHsc /W4  
#include <vector>  
#include <algorithm>  
#include <iostream>  
using namespace std;  
  
int main()  
{  
    // Create a vector that contains 3 elements.  
    vector<int> elements(3);  
  
    // Create another vector that contains index values.  
    vector<int> indices(3);  
    indices[0] = 0;  
    indices[1] = -1; // This is not a valid subscript. It will trigger an exception.  
    indices[2] = 2;  
  
    // Use the values from the vector of index values to   
    // fill the elements vector. This example uses a   
    // try/catch block to handle invalid access to the   
    // elements vector.  
    try  
    {  
        for_each(indices.begin(), indices.end(), [&](int index) {   
            elements.at(index) = index;   
        });  
    }  
    catch (const out_of_range& e)  
    {  
        cerr << "Caught '" << e.what() << "'." << endl;  
    };  
}  
```  
  
### Вывод  
  **Caught 'invalid vector\<T\> subscript'.**   
### Примечания  
 Дополнительные сведения об обработке исключений см. в разделе [Обработка исключений](../cpp/exception-handling-in-visual-cpp.md).  
  
 \[[Содержание этой статьи](#top)\]  
  
##  <a name="managedLambdaExpressions"></a> Использование лямбда\-выражений с управляемыми типами \(C\+\+\/CLI\)  
  
### Пример  
 Предложение захвата лямбда\-выражения не может содержать переменную, которая имеет управляемый тип.  Однако можно передать аргумент с управляемым типом в список параметров лямбда\-выражения.  В следующем примере содержится лямбда\-выражение, которое захватывает локальную неуправляемую переменную `ch` по значению и принимает объект <xref:System.String?displayProperty=fullName> в качестве параметра.  
  
### Код  
  
```cpp  
// managed_lambda_expression.cpp  
// compile with: /clr  
using namespace System;  
  
int main()  
{  
    char ch = '!'; // a local unmanaged variable  
  
    // The following lambda expression captures local variables  
    // by value and takes a managed String object as its parameter.  
    [=](String ^s) {   
        Console::WriteLine(s + Convert::ToChar(ch));   
    }("Hello");  
}  
  
```  
  
### Вывод  
  **Hello\!**   
### Примечания  
 Можно также использовать лямбда\-выражения с библиотекой STL\/CLR.  Дополнительные сведения см. в разделе [Библиотека STL\/CLR](../dotnet/stl-clr-library-reference.md).  
  
> [!IMPORTANT]
>  Лямбда\-выражения не поддерживаются в этих управляемых сущностях среды CLR: `ref class`, `ref struct`, `value class` и `value struct`.  
  
 \[[Содержание этой статьи](#top)\]  
  
## См. также  
 [Лямбда\-выражения](../cpp/lambda-expressions-in-cpp.md)   
 [Синтаксис лямбда\-выражений](../cpp/lambda-expression-syntax.md)   
 [auto](../cpp/auto-cpp.md)   
 [Класс function](../standard-library/function-class.md)   
 [find\_if](../Topic/find_if.md)   
 [\<algorithm\>](../standard-library/algorithm.md)   
 [Вызов функции](../Topic/Function%20Call%20\(C++\).md)   
 [Шаблоны](../Topic/Templates%20\(C++\).md)   
 [Обработка исключений](../cpp/exception-handling-in-visual-cpp.md)   
 [Библиотека STL\/CLR](../dotnet/stl-clr-library-reference.md)