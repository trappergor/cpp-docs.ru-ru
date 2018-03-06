---
title: "Auto (C++) | Документы Microsoft"
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
f1_keywords:
- auto_CPP
- auto
helpviewer_keywords:
- auto keyword [C++]
ms.assetid: e9d495d7-601c-4547-b897-998389a311f4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 334006e8ad06bdc174922d57d97d2d0f0335cf34
ms.sourcegitcommit: 4e01d36ffa64ea11bacf589f79d2f1df947e2510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2018
---
# <a name="auto-c"></a>Auto (C++)
Выводит тип объявленной переменной из выражения инициализации.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
auto declarator initializer;  
```  
  
```  
[](auto param1, auto param2) {};  
```  
  
## <a name="remarks"></a>Примечания  
 Ключевое слово `auto` указывает компилятору использовать выражение инициализации объявленной переменной, или параметр лямбда-выражения, чтобы вывести ее тип.  
  
 Ключевое слово `auto` рекомендуется использовать в большинстве ситуаций (кроме тех, когда требуется преобразование), поскольку оно обладает рядом преимуществ:  
  
-   **Надежность:** Если изменен тип выражения — числе Если изменен возвращаемый тип функции — это просто работает.  
  
-   **Производительность:** гарантирует, что будет существовать без преобразования.  
  
-   **Удобство использования:** не нужно беспокоиться о типа имя опечатках и ошибках.  
  
-   **Эффективность:** программирования может быть более эффективным.  
  
 Случаи преобразования, для которых не подходит ключевое слово `auto`:  
  
-   Если необходимо получить конкретный тип.  
  
-   Вспомогательные типы шаблона выражения — например, `(valarray+valarray)`.  
  
 Чтобы использовать ключевое слово `auto`, укажите его вместо типа для определения переменной, а затем задайте выражение инициализации. Кроме того, ключевое слово `auto` можно изменить с помощью спецификаторов и деклараторов, например `const`, `volatile`, указателя (`*`), ссылки (`&`) и ссылки rvalue `(&&`). Компилятор вычисляет выражение инициализации, а затем использует эти сведения, чтобы вывести тип переменной.  
  
 Выражение инициализации может представлять собой присваивание (синтаксис со знаком равенства), прямой инициализации (синтаксис в стиле функции), [оператор new](new-operator-cpp.md) выражение или выражение инициализации может быть  *для объявления диапазона* параметр в [инструкции (C++) на основе диапазонов](../cpp/range-based-for-statement-cpp.md) инструкции. Дополнительные сведения см. в разделе [инициализаторы](../cpp/initializers.md) и примеры кода далее в этом документе.  
  
 Ключевое слово `auto` является местозаполнителем для типа, однако само по себе не означает тип. Таким образом `auto` ключевое слово не может использоваться в приведениях типов или операторы например [sizeof](../cpp/sizeof-operator.md) и [typeid](../windows/typeid-cpp-component-extensions.md).  
  
## <a name="usefulness"></a>Удобство  
 Ключевое слово `auto` — это простой способ объявить переменную, которая имеет сложный тип. Например, с помощью `auto` можно объявить переменную, в которой выражение инициализации содержит шаблоны, указатели на функции или указатели на члены.  
  
 Кроме того, с помощью `auto` можно объявить и инициализировать переменную в лямбда-выражение. Вы не сможете самостоятельно объявить тип переменной, поскольку тип лямбда-выражения известен только компилятору. Дополнительные сведения см. в разделе [примеры лямбда-выражения](../cpp/examples-of-lambda-expressions.md).  
  
## <a name="trailing-return-types"></a>Отслеживание возвращаемых типов  
 Ключевое слово `auto` и спецификатор `decltype` помогают в написании библиотек шаблонов. Используйте `auto` и `decltype` для объявления функции шаблонов, возвращаемый тип которой зависит от типов аргументов его шаблонов. Кроме того, при помощи `auto` и `decltype` можно объявить шаблонную функцию, которая создает оболочку для вызова другой функции, а потом возвращает полученный результат, какой бы возвращаемый тип ни имела вторая функция. Дополнительные сведения см. в разделе [decltype](../cpp/decltype-cpp.md).  
  
## <a name="references-and-cv-qualifiers"></a>Ссылки и cv-квалификаторы  
 Обратите внимание, что использование `auto` удаляет ссылки, квалификаторы const и квалификаторы volatile. Рассмотрим следующий пример.  
  
```cpp  
// cl.exe /analyze /EHsc /W4  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
    int count = 10;  
    int& countRef = count;  
    auto myAuto = countRef;  
  
    countRef = 11;  
    cout << count << " ";  
  
    myAuto = 12;  
    cout << count << endl;  
}  
  
```  
  
 В предыдущем примере myAuto является объектом типа int, не ссылки на тип int, поэтому программа выводит `11 11`, а не `11 12` как может произойти, если ссылочный квалификатор не был удален процессом `auto`.  
  
## <a name="type-deduction-with-braced-initializers-c14"></a>Выведение типа с инициализаторами заключенного в фигурные скобки (C ++ 14)  
 Следующий код exmample показано, как для инициализации переменной автоматически с помощью скобок. Обратите внимание на разницу между B и C, а также между A и E.  
  
```cpp  
#include <initializer_list>  
  
int main()  
{  
    // std::initializer_list<int>  
    auto A = { 1, 2 };  
  
    // std::initializer_list<int>  
    auto B = { 3 };  
  
    // int  
    auto C{ 4 };  
  
    // C3535: cannot deduce type for 'auto' from initializer list'  
    auto D = { 5, 6.7 };  
  
    // C3518 in a direct-list-initialization context the type for 'auto'  
    // can only be deduced from a single initializer expression  
    auto E{ 8, 9 };  
  
    return 0;  
}  
```  
  
## <a name="restrictions-and-error-messages"></a>Ограничения и сообщения об ошибках  
 В приведенной ниже таблице перечислены ограничения на использование ключевого слова `auto` и соответствующие диагностические сообщения об ошибках, которые выводит компилятор.  
  
|Номер ошибки|Описание:|  
|------------------|-----------------|  
|[C3530](../error-messages/compiler-errors-2/compiler-error-c3530.md)|Ключевое слово `auto` не может использоваться в сочетании с другим спецификатором типа.|  
|[C3531](../error-messages/compiler-errors-2/compiler-error-c3531.md)|Символ, объявленный с помощью ключевого слова `auto`, должен иметь инициализатор.|  
|[C3532](../error-messages/compiler-errors-2/compiler-error-c3532.md)|Неверно используется ключевое слово `auto` для объявления типа. Например, был объявлен тип возвращаемого значения метода или массив.|  
|[C3533](../error-messages/compiler-errors-2/compiler-error-c3533.md), [C3539](../error-messages/compiler-errors-2/compiler-error-c3539.md)|Аргумент параметра или шаблона не может объявляться с помощью ключевого слова `auto`.|  
|[C3535](../error-messages/compiler-errors-2/compiler-error-c3535.md)|Параметр метода или шаблона не может объявляться с помощью ключевого слова `auto`.|  
|[C3536](../error-messages/compiler-errors-2/compiler-error-c3536.md)|Символ не может быть использован до инициализации. Практически это означает, что переменную нельзя использовать для инициализации самой себя.|  
|[C3537](../error-messages/compiler-errors-2/compiler-error-c3537.md)|Выполнить приведение к типу, объявленному с помощью ключевого слова `auto`, невозможно.|  
|[C3538](../error-messages/compiler-errors-2/compiler-error-c3538.md)|Все символы в списке деклараторов, объявленные при помощи ключевого слова `auto`, должны разрешаться к одному и тому же типу. Дополнительные сведения см. в разделе [объявления и определения](declarations-and-definitions-cpp.md).|  
|[C3540](../error-messages/compiler-errors-2/compiler-error-c3540.md), [C3541](../error-messages/compiler-errors-2/compiler-error-c3541.md)|[Sizeof](../cpp/sizeof-operator.md) и [typeid](../windows/typeid-cpp-component-extensions.md) операторы не может применяться на символ, объявленный с `auto` ключевое слово.|  
  
## <a name="examples"></a>Примеры  
 В следующих фрагментах кода показаны ситуации, в которых может использоваться ключевое слово `auto`.  
  
 Следующие объявления эквивалентны. В первом операторе переменная `j` объявлена с типом `int`. Во втором операторе выводится, что переменная `k` имеет тип `int`, поскольку выражение инициализации (0) является целым числом.  
  
```cpp  
int j = 0;  // Variable j is explicitly type int.  
auto k = 0; // Variable k is implicitly type int because 0 is an integer.  
```  
  
 Следующие объявления эквивалентны, но второе объявление проще первого. Одной из важнейших причин, по которым следует использовать ключевое слово `auto`, является простота.  
  
```cpp  
map<int,list<string>>::iterator i = m.begin();   
auto i = m.begin();   
```  
  
 В следующем фрагменте кода тип переменных `iter` и `elem` объявляется при запуске цикла `for` и диапазона `for`.  
  
```cpp  
// cl /EHsc /nologo /W4  
#include <deque>  
using namespace std;  
  
int main()  
{  
    deque<double> dqDoubleData(10, 0.1);  
  
    for (auto iter = dqDoubleData.begin(); iter != dqDoubleData.end(); ++iter)  
    { /* ... */ }  
  
    // prefer range-for loops with the following information in mind  
    // (this applies to any range-for with auto, not just deque)  
  
    for (auto elem : dqDoubleData) // COPIES elements, not much better than the previous examples  
    { /* ... */ }  
  
    for (auto& elem : dqDoubleData) // observes and/or modifies elements IN-PLACE  
    { /* ... */ }  
  
    for (const auto& elem : dqDoubleData) // observes elements IN-PLACE  
    { /* ... */ }  
}  
```  
  
 В следующем примере кода объявляется указатель. Для этого используется оператор `new` и объявление указателя.  
  
```cpp  
double x = 12.34;  
auto *y = new auto(x), **z = new auto(&x);  
```  
  
 В следующем примере кода объявлено несколько символов в каждом операторе объявления. Обратите внимание, что все символы во всех операторах разрешаются к одному и тому же типу.  
  
```cpp  
auto x = 1, *y = &x, **z = &y; // Resolves to int.  
auto a(2.01), *b (&a);         // Resolves to double.  
auto c = 'a', *d(&c);          // Resolves to char.  
auto m = 1, &n = m;            // Resolves to int.  
```  
  
 В этом примере кода используется условный оператор (`?:`). Переменная `x` здесь объявляется как целочисленная переменная со значением 200.  
  
```cpp  
int v1 = 100, v2 = 200;  
auto x = v1 > v2 ? v1 : v2;  
```  
  
 В следующем фрагменте кода инициализирует переменную `x` ввода `int`, переменная `y` ссылка на тип `const int`и переменная `fp` в указатель на функцию, возвращающую тип `int`.  
  
```cpp  
int f(int x) { return x; }  
int main()  
{  
    auto x = f(0);  
    const auto & y = f(1);  
    int (*p)(int x);  
    p = f;  
    auto fp = p;  
    //...  
}  
```  
  
## <a name="see-also"></a>См. также  
 [auto Keyword](../cpp/auto-keyword.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [/ Zc: auto (выведение типа переменной)](../build/reference/zc-auto-deduce-variable-type.md)   
 [Оператор sizeof](../cpp/sizeof-operator.md)   
 [typeid](../windows/typeid-cpp-component-extensions.md)   
 [оператор new](new-operator-cpp.md)   
 [Объявления и определения](declarations-and-definitions-cpp.md)   
 [Примеры лямбда-выражений](../cpp/examples-of-lambda-expressions.md)   
 [Инициализаторы](../cpp/initializers.md)   
 [decltype](../cpp/decltype-cpp.md)