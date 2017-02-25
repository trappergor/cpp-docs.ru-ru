---
title: "Единообразная инициализация и делегирование конструкторов | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: aa4daa64-eaec-4a3c-ade4-d9325e31e9d4
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Единообразная инициализация и делегирование конструкторов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В современном C\+\+, можно использовать *инициализация фигурных скобок* для любого типа, без знака равенства.  Кроме того, можно использовать конструкторы делегировании, чтобы упростить код, если имеется несколько конструкторов, которые выполняют как работы.  
  
## Инициализация фигурных скобок  
 Инициализация фигурных скобок можно использовать для любого класса, структуры или объединения.  Если тип конструктор по умолчанию, неявно или явно объявил, можно использовать значения по умолчанию инициализация фигурной скобки \(с пустыми фигурные скобки\).  Например, следующий класс может быть инициализирован с помощью и по умолчанию и инициализации фигурной скобки не по умолчанию.  
  
```cpp  
#include <string>  
using namespace std;  
  
class class_a {  
public:  
    class_a() {}  
    class_a(string str) : m_string{ str } {}  
    class_a(string str, double dbl) : m_string{ str }, m_double{ dbl } {}  
double m_double;  
string m_string;  
};  
  
int main()  
{  
    class_a c1{};  
    class_a c1_1;  
  
    class_a c2{ "ww" };  
    class_a c2_1("xx");  
  
    // order of parameters is the same as the constructor  
    class_a c3{ "yy", 4.4 };  
    class_a c3_1("zz", 5.5);  
}  
  
```  
  
 Если класс имеет конструкторы не по умолчанию, порядок, в котором члены класса указываются в инициализатор фигурных скобок, порядок, в котором соответствующие параметры отображаются в конструкторе, не порядок, в котором указываются участники \(как с `class_a` в предыдущем примере\).  В противном случае если тип, объявленный не имеет конструктор, порядок, в котором члены появятся в инициализатор фигурной скобки не то же самое, что порядок, в котором она объявлена. в этом случае можно инициализировать любое количество открытых членов по мере необходимости, но нельзя пропустить любого члена.  В следующем примере показан порядок, используемый при инициализации фигурной скобки при отсутствии у конструктора:  
  
```cpp  
class class_d {  
public:  
    float m_float;  
    string m_string;  
    wchar_t m_char;  
};  
  
int main()  
{  
    class_d d1{};  
    class_d d1{ 4.5 };  
    class_d d2{ 4.5, "string" };  
    class_d d3{ 4.5, "string", 'c' };  
  
    class_d d4{ "string", 'c' }; // compiler error  
    class_d d5("string", 'c', 2.0 }; // compiler error  
}   
```  
  
 При объявлении, но помечают конструктор по умолчанию явно как удаляется, инициализацию фигурных скобок по умолчанию нельзя использовать:  
  
```cpp  
class class_f {  
public:  
    class_f() = delete;  
    class_f(string x): m_string { x } {}  
    string m_string;  
};  
int main()  
{  
    class_f cf{ "hello" };  
    class_f cf1{}; // compiler error C2280: attempting to reference a deleted function  
}  
```  
  
 Инициализация фигурных скобок можно использовать везде, где обычно выполнить инициализация\- для примера, в качестве параметра функции или возвращаемое значение, или с помощью ключевого слова `new`:  
  
```cpp  
class_d* cf = new class_d{4.5};  
kr->add_d({ 4.5 });  
return { 4.5 };  
  
```  
  
## конструкторы initializer\_list  
 [initializer\_list Class](../standard-library/initializer-list-class.md) представляет список объектов указанного типа, который можно использовать в конструкторе, и в других контекстах.  Можно создать initializer\_list инициализации с помощью фигурных скобок.  
  
```cpp  
initializer_list<int> int_list{5, 6, 7};  
```  
  
> [!IMPORTANT]
>  Чтобы использовать этот класс, необходимо включить заголовок [\<initializer\_list\>](../standard-library/initializer-list.md).  
  
 `initializer_list` можно скопировать.  В этом случае членов нового списка ссылок на члены исходный список:  
  
```cpp  
initializer_list<int> ilist1{ 5, 6, 7 };  
initializer_list<int> ilist2( ilist1 );  
if (ilist1.begin() == ilist2.begin())  
    cout << "yes" << endl; // expect "yes"  
  
```  
  
 Стандартные библиотеки классов контейнера, а также `string`, `wstring` и `regex`, имеющие конструкторы `initializer_list`.  В следующих примерах демонстрируется инициализация фигурных скобок задачи с этими конструкторами:  
  
```cpp  
vector<int> v1{ 9, 10, 11 };   
map<int, string> m1{ {1, "a"}, {2, "b"} };  
string s{ 'a', 'b', 'c' };   
regex rgx{'x', 'y', 'z'};   
```  
  
## Делегирующие конструкторы  
 Многие классы имеют несколько конструкторов, которые выполняют аналогичную действие\- для примера, проверяют параметры:  
  
```cpp  
class class_c {  
public:  
    int max;  
    int min;  
    int middle;  
  
    class_c() {}  
    class_c(int my_max) {   
        max = my_max > 0 ? my_max : 10;   
    }  
    class_c(int my_max, int my_min) {   
        max = my_max > 0 ? my_max : 10;  
        min = my_min > 0 && my_min < max ? my_min : 1;  
    }  
    class_c(int my_max, int my_min, int my_middle) {  
        max = my_max > 0 ? my_max : 10;  
        min = my_min > 0 && my_min < max ? my_min : 1;  
        middle = my_middle < max && my_middle > min ? my_middle : 5;  
    }  
};  
```  
  
 Можно уменьшить повторяющегося кода можно добавить функцию, которая выполняет полную проверку, но код для `class_c` будет проще для понимания и поддерживать один конструктор может делегировать часть работы один в другой.  Чтобы добавить делегировании конструкторы, используйте синтаксис `constructor (. . .) : constructor (. . .)`:  
  
```cpp  
class class_c {  
public:  
    int max;  
    int min;  
    int middle;  
  
    class_c(int my_max) {   
        max = my_max > 0 ? my_max : 10;   
    }  
    class_c(int my_max, int my_min) : class_c(my_max) {   
        min = my_min > 0 && my_min < max ? my_min : 1;  
    }  
    class_c(int my_max, int my_min, int my_middle) : class_c (my_max, my_min){  
        middle = my_middle < max && my_middle > min ? my_middle : 5;  
}  
};  
int main() {  
  
    class_c c1{ 1, 3, 2 };  
}  
  
```  
  
 Как и пройти предыдущий пример, обратите внимание, что сначала вызывает `class_c(int, int, int)` конструктора конструктор `class_c(int, int)`, который, в свою очередь, вызывает `class_c(int)`.  Каждый из конструкторов выполняет только работы, не выполняется другими конструкторами.  
  
 Первый конструктор, который инициализирует объект вызывается, чтобы все его члены инициализируются в этой точке.  Невозможно выполнить инициализацию членов в конструкторе, делегирует другому конструктору, как показано ниже:  
  
```cpp  
class class_a {  
public:  
    class_a() {}  
    // member initialization here, no delegate  
    class_a(string str) : m_string{ str } {}  
  
    //can’t do member initialization here  
    // error C3511: a call to a delegating constructor shall be the only member-initializer  
    class_a(string str, double dbl) : class_a(str) , m_double{ dbl } {}  
  
    // only member assignment  
    class_a(string str, double dbl) : class_a(str) { m_double = dbl; }  
    double m_double{ 1.0 };  
    string m_string;  
};  
  
```  
  
 В следующем примере показано использование не статических инициализаторов элемента данных.  Обратите внимание, что если конструктор также инициализирует заданный элемент данных, инициализации членов переопределена.  
  
```cpp  
class class_a {  
public:  
    class_a() {}  
    class_a(string str) : m_string{ str } {}  
    class_a(string str, double dbl) : class_a(str) { m_double = dbl; }  
    double m_double{ 1.0 };  
    string m_string{ m_double < 10.0 ? "alpha" : "beta" };  
};  
  
int main() {  
    class_a a{ "hello", 2.0 };  //expect a.m_double == 2.0, a.m_string == "hello"  
    int y = 4;  
}  
```  
  
 Синтаксис делегирования конструктора не предотвращает случайное создание вызовов Constructor2 конструктора recursion\-Constructor1, вызывает Constructor1\-and ошибок не создаются до тех пор, пока не переполнения стека.  За избежать циклов.  
  
```cpp  
class class_f{  
public:  
    int max;  
    int min;  
  
    // don't do this  
    class_f() : class_f(6, 3){ }  
    class_f(int my_max, int my_min) : class_f() { }  
};  
```