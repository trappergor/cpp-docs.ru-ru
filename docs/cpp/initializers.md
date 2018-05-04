---
title: Инициализаторы | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- array-element initializers
- initializing arrays [C++], initializers
- arrays [C++], array-element initializers
- declarators, as initializers
- initializers, array element
ms.assetid: ce301ed8-aa1c-47b2-bb39-9f0541b4af85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 072b6a62bde2ab58909fd0c8dd1954e7d330ced5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="initializers"></a>Инициализаторы
Инициализатор определяет начальное значение переменной. Можно инициализировать переменные в этих контекстах:  
  
-   В определении переменной:  
  
    ```cpp  
    int i = 3;  
    Point p1{ 1, 2 };  
    ```  
  
-   В качестве одного из параметров функции:  
  
    ```cpp  
    set_point(Point{ 5, 6 });  
    ```  
  
-   В качестве возвращаемого типа функции:  
  
    ```cpp  
    Point get_new_point(int x, int y) { return { x, y }; }  
    Point get_new_point(int x, int y) { return Point{ x, y }; }  
  
    ```  
  
 Инициализаторы могут принимать эти формы:  
  
-   Выражение (или разделенный запятыми список выражений) в скобках:  
  
    ```cpp  
    Point p1(1, 2);  
    ```  
  
-   Знак равенства с последующим выражением:  
  
    ```cpp  
    string s = "hello";  
    ```  
  
-   Список инициализации в фигурных скобках. Список может быть пустым или может состоять из набора списков как в приведенном ниже примере.  
  
    ```cpp  
    struct Point{  
        int x;  
        int y;  
    };  
    class PointConsumer{  
    public:  
        void set_point(Point p){};  
        void set_points(initializer_list<Point> my_list){};  
    };  
    int main() {  
        PointConsumer pc{};  
        pc.set_point({});  
        pc.set_point({ 3, 4 });  
        pc.set_points({ { 3, 4 }, { 5, 6 } });  
    }  
    ```  
  
## <a name="kinds-of-initialization"></a>Типы инициализации  
 Существует несколько типов инициализации, которые могут встречаться на различных этапах выполнения программы. Различные типы инициализации не является взаимоисключающими, например, инициализация списка может активировать инициализацию значений, а в других условиях она может активировать агрегатную инициализацию.  
  
### <a name="zero-initialization"></a>Нулевая инициализация  
 Нулевая инициализация — задание для переменной нулевого значения, неявно преобразованного в тип:  
  
-   Числовые переменные инициализируются значением 0 (или 0,0; 0,0000000000 и т.п.).  
  
-   Переменные char инициализируются `'\0'`.  
  
-   Указатели инициализируются значением `nullptr`.  
  
-   Массивы, [POD](../standard-library/is-pod-class.md) классов, структур и объединений имеют члены инициализируется нулевым значением.  
  
 Нулевая инициализация выполняется в разное время:  
  
-   При запуске программы — для всех именованных переменных, имеющих статическую длительность. Далее эти переменные могут быть инициализированы повторно.  
  
-   Во время инициализации значений — для скалярных типов и типов класса POD, которые инициализируются с помощью пустых фигурных скобок.  
  
-   Для массивов, у которых инициализировано только подмножество членов.  
  
 Ниже приведены некоторые примеры нулевой инициализации:  
  
```cpp  
struct my_struct{  
    int i;  
    char c;  
};  
  
int i0;              // zero-initialized to 0  
int main() {  
    static float f1;  // zero-initialized to 0.000000000  
    double d{};     // zero-initialized to 0.00000000000000000  
    int* ptr{};     // initialized to nullptr  
    char s_array[3]{'a', 'b'};  // the third char is initialized to '\0'  
    int int_array[5] = { 8, 9, 10 };  // the fourth and fifth ints are initialized to 0  
    my_struct a_struct{};   // i = 0, c = '\0'  
}  
```  
  
### <a name="default_initialization"></a> Инициализация по умолчанию  
 Инициализация по умолчанию для классов, структур и объединений — это инициализация с помощью конструктора по умолчанию. Конструктор по умолчанию можно вызвать без выражения инициализации или с использованием ключевого слова `new`:  
  
```cpp  
MyClass mc1;  
MyClass* mc3 = new MyClass;  
```  
  
 Если класс, структура или объединение не имеет конструктор по умолчанию, компилятор выдает ошибку.  
  
 Скалярные переменные инициализируются по умолчанию, если при их определении не указываются выражения инициализации. Они имеют неопределенные значения.  
  
```cpp  
int i1;  
float f;  
char c;  
```  
  
 Массивы инициализируются по умолчанию, если при их определении не указываются выражения инициализации. Если массив инициализируется по умолчанию, его члены инициализируются по умолчанию и приобретают неопределенные значения как в приведенном ниже примере.  
  
```cpp  
int int_arr[3];  
```  
  
 Если члены массива не имеют конструктор по умолчанию, компилятор выдает ошибку.  
  
#### <a name="default-initialization-of-constant-variables"></a>Инициализация по умолчанию константных переменных  
 Константные переменные необходимо объявлять вместе с инициализатором. Если они относятся к скалярным типам, они вызывают ошибку компилятора, а если они относятся к типам классов, имеющим конструктор по умолчанию, они вызывают предупреждение:  
  
```cpp  
class MyClass{};  
int main() {  
    //const int i2;   // compiler error C2734: const object must be initialized if not extern  
    //const char c2;  // same error  
    const MyClass mc1; // compiler error C4269: 'const automatic data initialized with compiler generated default constructor produces unreliable results  
}  
```  
  
#### <a name="default-initialization-of-static-variables"></a>Инициализация по умолчанию статических переменных  
 Статические переменные, объявленные без инициализатора, инициализируются значением 0 (с неявным преобразованием к соответствующему типу).  
  
```cpp  
class MyClass {     
private:  
    int m_int;  
    char m_char;  
};  
  
int main() {  
    static int int1;       // 0  
    static char char1;     // '\0'  
    static bool bool1;   // false  
    static MyClass mc1;     // {0, '\0'}  
}  
```  
  
 Дополнительные сведения об инициализации глобальных статических объектов см. в разделе [Дополнительные сведения о запуске](../cpp/additional-startup-considerations.md).  
  
### <a name="value-initialization"></a>Инициализация значения  
 Инициализация значения происходит в следующих случаях:  
  
-   Именованное значение инициализируется с использованием пустых фигурных скобок.  
  
-   Анонимный временный объект инициализируется с помощью пустых круглых или фигурных скобок.  
  
-   Объект инициализируется с помощью ключевого слова `new` и пустых круглых или фигурных скобок.  
  
 При инициализации значения выполняются следующие действия:  
  
-   Для классов, имеющих хотя бы один открытый конструктор, вызывается конструктор по умолчанию.  
  
-   В случае классов, не относящихся к объединениям, у которых нет объявленных конструкторов, объект инициализируется нулевым значением, и вызывается конструктор по умолчанию.  
  
-   В случае массивов каждый элемент инициализируется значением.  
  
-   Во всех остальных случаях переменная инициализируется нулевым значением.  
  
```cpp  
class BaseClass {    
private:  
    int m_int;  
};  
  
int main() {  
    BaseClass bc{};     // class is initialized  
    BaseClass*  bc2 = new BaseClass();  // class is initialized, m_int value is 0  
    int int_arr[3]{};  // value of all members is 0  
    int a{};     // value of a is 0  
    double b{};  // value of b is 0.00000000000000000  
}  
  
```  
  
### <a name="copy-initialization"></a>Инициализация копированием  
 Инициализация копированием — это инициализация одного объекта с использованием другого объекта. Она выполняется в следующих случаях:  
  
-   Переменная инициализируется с помощью знака равенства.  
  
-   Аргумент передается в функцию.  
  
-   Объект возвращается функцией.  
  
-   Возникает или перехватывается исключение.  
  
-   Нестатический элемент данных инициализируется с помощью знака равенства.  
  
-   Класс, структура и члены объединения инициализируются с применением инициализации путем копирования во время агрегатной инициализации. В разделе [агрегатной инициализации](#agginit) примеры.  
  
 Следующий код демонстрирует несколько примеров инициализации копированием.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
class MyClass{  
public:  
    MyClass(int myInt) {}  
    void set_int(int myInt) { m_int = myInt; }  
    int get_int() const { return m_int; }  
private:  
    int m_int = 7; // copy initialization of m_int  
  
};  
class MyException : public exception{};  
int main() {  
    int i = 5;              // copy initialization of i  
    MyClass mc1{ i };  
    MyClass mc2 = mc1;      // copy initialization of mc2 from mc1  
    MyClass mc1.set_int(i);    // copy initialization of parameter from i  
    int i2 = mc2.get_int(); // copy initialization of i2 from return value of get_int()  
  
    try{  
        throw MyException();      
    }  
    catch (MyException ex){ // copy initialization of ex  
        cout << ex.what();    
    }  
}  
```  
  
 Инициализация копированием не может вызывать явные конструкторы.  
  
```cpp  
vector<int> v = 10; // the constructor is explicit; compiler error C2440: cannot convert from 'int' to 'std::vector<int,std::allocator<_Ty>>'  
regex r = "a.*b"; // the constructor is explicit; same error  
shared_ptr<int> sp = new int(1729); // the constructor is explicit; same error  
```  
  
 В некоторых случаях, если конструктор копии класса удален или недоступен, копируемая инициализация вызывает ошибку компилятора. 
  
### <a name="direct-initialization"></a>Прямая инициализация  
 Прямая инициализация — это инициализация с использованием (непустых) круглых или фигурных скобок. В отличие от копируемой инициализации она может вызывать явные конструкторы. Она выполняется в следующих случаях:  
  
-   Переменная инициализируется с помощью непустых круглых или фигурных скобок.  
  
-   Переменная инициализируется с помощью ключевого слова `new` и непустых круглых или фигурных скобок.  
  
-   Переменная инициализируется с помощью `static_cast`.  
  
-   В конструкторе базовые классы и нестатические члены инициализируются с помощью списка инициализации.  
  
-   В копии захваченной переменной в лямбда-выражении.  
  
 Приведенный ниже код демонстрирует несколько примеров прямой инициализации.  
  
```cpp  
class BaseClass{  
public:  
    BaseClass(int n) :m_int(n){} // m_int is direct initialized  
private:  
    int m_int;  
};  
  
class DerivedClass : public BaseClass{  
public:  
    // BaseClass and m_char are direct initialized  
    DerivedClass(int n, char c) : BaseClass(n), m_char(c) {}  
private:  
    char m_char;  
};  
int main(){  
    BaseClass bc1(5);  
    DerivedClass dc1{ 1, 'c' };  
    BaseClass* bc2 = new BaseClass(7);  
    BaseClass bc3 = static_cast<BaseClass>(dc1);  
  
    int a = 1;  
    function<int()> func = [a](){  return a + 1; }; // a is direct initialized  
    int n = func();  
}  
```  
  
### <a name="list-initialization"></a>Инициализация списком  
 Инициализация списком выполняется, когда переменная инициализируется с помощью списка инициализации в фигурных скобках. Списки инициализации в фигурных скобках можно использовать в следующих случаях:  
  
-   Инициализируется переменная.  
  
-   Инициализируется класс с помощью ключевого слова `new`.  
  
-   Объект возвращается функцией.  
  
-   Аргумент передается функции.  
  
-   Один из аргументов при прямой инициализации.  
  
-   В инициализаторе нестатических элементов данных.  
  
-   В списке инициализации конструктора.  
  
 Приведенный ниже код демонстрирует несколько примеров инициализации списком.  
  
```cpp  
class MyClass {  
public:  
    MyClass(int myInt, char myChar) {}    
private:  
    int m_int[]{ 3 };  
    char m_char;  
};  
class MyClassConsumer{  
public:  
    void set_class(MyClass c) {}  
    MyClass get_class() { return MyClass{ 0, '\0' }; }  
};  
struct MyStruct{  
    int my_int;  
    char my_char;  
    MyClass my_class;  
};  
int main() {  
    MyClass mc1{ 1, 'a' };  
    MyClass* mc2 = new MyClass{ 2, 'b' };  
    MyClass mc3 = { 3, 'c' };  
  
    MyClassConsumer mcc;  
    mcc.set_class(MyClass{ 3, 'c' });  
    mcc.set_class({ 4, 'd' });  
  
    MyStruct ms1{ 1, 'a', { 2, 'b' } };  
}  
```  
  
### <a name="agginit"></a> Агрегатная инициализация  
 Агрегатная инициализация — форма инициализации списка для массивов и типов классов (часто структур и объединений), со следующими характеристиками:  
  
-   Отсутствие закрытых или защищенных членов.  
  
-   Отсутствие заданных пользователем конструкторов кроме явно заданных по умолчанию или удаленных конструкторов.  
  
-   Отсутствие базовых классов.  
  
-   Отсутствие виртуальных функций-членов.  
  
> [!NOTE]
>  <!--conformance note-->In Visual Studio 2015 and earlier, an aggregate is not allowed to have  brace-or-equal initializers for non-static members. This restriction was removed in the C++14 standard and implemented in Visual Studio 2017. 
  
 Агрегатные инициализаторы состоят из списка инициализации в фигурных скобках со знаком равенства или без него как в приведенном ниже примере:  
  
```cpp  
#include <iostream>  
using namespace std;  
  
struct MyAggregate{  
    int myInt;  
    char myChar;  
};  
  
int main() {  
    MyAggregate agg1{ 1, 'c' };  
  
    cout << "agg1: " << agg1.myChar << ": " << agg1.myInt << endl;  
    cout << "agg2: " << agg2.myChar << ": " << agg2.myInt << endl;  
  
    int myArr1[]{ 1, 2, 3, 4 };  
    int myArr2[3] = { 5, 6, 7 };  
    int myArr3[5] = { 8, 9, 10 };  
  
    cout << "myArr1: ";  
    for (int i : myArr1){  
        cout << i << " ";  
    }  
    cout << endl;  
  
    cout << "myArr3: ";  
    for (auto const &i : myArr3) {  
        cout << i << " ";  
    }  
    cout << endl;  
}  
```  
  
 Должны выводиться следующие данные:  
  
```  
agg1: c: 1  
agg2: d: 2  
myArr1: 1 2 3 4  
myArr3: 8 9 10 0 0  
```  
  
> [!IMPORTANT]
>  Элементы массива, которые объявлены, но не инициализируются явно во время агрегатной инициализации инициализируются нулевым значением, как и в `myArr3` выше.  
  
#### <a name="initializing-unions-and-structs"></a>Инициализация объединений и структур  
 Если объединение не имеет конструктора, его можно инициализировать одним значением (или другим экземпляром объединения). Значение используется для инициализации первого нестатического поля. Это отличается от инициализации структур, где первое значение в инициализаторе используется для инициализации первого поля, второе — для инициализации второго поля и т. д. Сравните инициализацию объединений и структур в следующем примере:  
  
```cpp  
struct MyStruct {  
    int myInt;  
    char myChar;  
};  
union MyUnion {  
    int my_int;  
    char my_char;  
    bool my_bool;  
    MyStruct my_struct;  
};  
  
int main() {    
    MyUnion mu1{ 'a' };  // my_int = 97, my_char = 'a', my_bool = true, {myInt = 97, myChar = '\0'}  
    MyUnion mu2{ 1 };   // my_int = 1, my_char = 'x1', my_bool = true, {myInt = 1, myChar = '\0'}  
    MyUnion mu3{};      // my_int = 0, my_char = '\0', my_bool = false, {myInt = 0, myChar = '\0'}  
    MyUnion mu4 = mu3;  // my_int = 0, my_char = '\0', my_bool = false, {myInt = 0, myChar = '\0'}  
    //MyUnion mu5{ 1, 'a', true };  // compiler error: C2078: too many initializers  
    //MyUnion mu6 = 'a';            // compiler error: C2440: cannot convert from 'char' to 'MyUnion'  
    //MyUnion mu7 = 1;              // compiler error: C2440: cannot convert from 'int' to 'MyUnion'  
  
    MyStruct ms1{ 'a' };            // myInt = 97, myChar = '\0'  
    MyStruct ms2{ 1 };              // myInt = 1, myChar = '\0'  
    MyStruct ms3{};                 // myInt = 0, myChar = '\0'  
    MyStruct ms4{1, 'a'};           // myInt = 1, myChar = 'a'  
    MyStruct ms5 = { 2, 'b' };      // myInt = 2, myChar = 'b'  
}  
```  
  
#### <a name="initializing-aggregates-that-contain-aggregates"></a>Инициализация статистических выражений, содержащих статистические выражения  
 Агрегатные типы могут содержать другие агрегатные типы, например массивы массивов, массивы структур и т. п. Эти типы инициализируются с помощью вложенных наборов фигурных скобок, как показано в следующем примере:  
  
```cpp  
struct MyStruct {  
    int myInt;  
    char myChar;  
};  
int main() {  
    int intArr1[2][2]{{ 1, 2 }, { 3, 4 }};  
    int intArr3[2][2] = {1, 2, 3, 4};    
    MyStruct structArr[]{ { 1, 'a' }, { 2, 'b' }, {3, 'c'} };  
}  
```  
  
### <a name="reference-initialization"></a>Инициализация ссылок  
 Переменные ссылочного типа должны инициализироваться объектом типа, на котором основан ссылочный тип, или объектом типа, который можно преобразовать в такой тип. Пример:  
  
```  
// initializing_references.cppint   
int iVar;  
long lVar;  
int main()   
{   long& LongRef1 = lVar;   // No conversion required.  
   long& LongRef2 = iVar;   // C2440  
   const long& LongRef3 = iVar;   // OK  
   LongRef1 = 23L;   // Change lVar through a reference.  
   LongRef2 = 11L;   // Change iVar through a reference.  
   LongRef3 = 11L;   // C3892}  
```  
  
 Единственный способ инициализировать ссылку с помощью временного объекта является инициализация постоянного временного объекта. После инициализации переменная ссылочного типа всегда указывает на один и тот же объект; ее невозможно изменить, чтобы она указывала на другой объект.  
  
 Хотя синтаксис может быть одинаковым, инициализация переменных ссылочного типа и присваивание значений переменным ссылочного типа семантически различаются. В предыдущем примере присваивания, которые изменяют значения переменных `iVar` и `lVar`, выглядят аналогично инициализации, но имеют другой эффект. Инициализация определяет объект, на который указывает переменная ссылочного типа; при присваивании через ссылку производится присваивание значения объекту, на который указывает ссылка.  
  
 Поскольку передача аргумента ссылочного типа в функцию и возврат значения ссылочного типа из функции являются инициализацией, формальные аргументы функции, а также возвращаемые ссылки инициализируются правильно.  
  
 Переменные ссылочного типа можно объявлять без инициализаторов только в указанных ниже случаях.  
  
-   Объявления функций (прототипы). Пример:  
  
    ```  
    int func( int& );  
    ```  
  
-   Объявления типов, возвращаемых функцией. Пример:  
  
    ```  
    int& func( int& );  
    ```  
  
-   Объявления члена класса ссылочного типа. Пример:  
  
    ```  
    class c {public:   int& i;};  
    ```  
  
-   Объявление переменной, явно указанной как `extern`. Пример:  
  
    ```  
    extern int& iVal;  
    ```  
  
 При инициализации переменной ссылочного типа компилятор с помощью графа принятия решений, показанного на следующем рисунке, выбирает между созданием ссылки на объект и созданием временного объекта, на который указывает ссылка.  
  
 ![Граф принятия решений для инициализации типов ссылок](../cpp/media/vc38s71.gif "vc38S71")  
Граф принятия решений для инициализации ссылочных типов  
  
 Ссылки на `volatile` типов (объявленные как `volatile` *typename *** &** *идентификатор*) можно инициализировать с `volatile` объектов того же типа или с объекты, которые не были объявлены как `volatile`. Их нельзя, однако, инициализируемый **const** объектов этого типа. Аналогично, ссылки на **const** типов (объявленные как **const** *typename *** &** *идентификатор*) может быть инициализируется **const** объектов того же типа (или все, что имеется преобразование для этого типа или с объектами, которые не были объявлены как **const**). Однако их невозможно инициировать с помощью объектов `volatile` этого типа.  
  
 Ссылки, которые не дополняются либо **const** или `volatile` ключевое слово может инициализироваться только значением объекты, объявленные как ни **const** , ни `volatile`.  
  
### <a name="initialization-of-external-variables"></a>Инициализация внешних переменных  
 Объявления автоматических, статических и внешних переменных могут содержать инициализаторы. Однако объявления внешних переменных могут содержать инициализаторы, только если эти переменные не объявлены как `extern`.
  
