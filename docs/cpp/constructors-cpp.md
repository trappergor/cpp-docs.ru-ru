---
title: "Конструкторы (C++) | Документы Microsoft"
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
- constructors [C++]
- objects [C++], creating
- instance constructors
ms.assetid: 3e9f7211-313a-4a92-9584-337452e061a9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 57854ec15d3104d80e8dbba68ebc33937222172f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="constructors-c"></a>Конструкторы (C++)
Конструктор — это особая функция-член, инициализирующая экземпляр своего класса. Конструкторы имеют имена, совпадающие с именами классов, и не имеют возвращаемых значений. У конструктора может быть любое число параметров, а у класса — любое число перегруженных конструкторов. Конструкторы могут иметь любой уровень доступа — открытый, защищенный или закрытый. Если вы не определили ни одного конструктора, компилятор создаст конструктор по умолчанию, не имеющий параметров. Это поведение можно переопределить, объявив конструктор по умолчанию как удаленный.  
  
## <a name="in-this-topic"></a>Содержание раздела  
  
-   [Порядок создания](#order_of_construction)  
  
-   [Списки членов](#member_lists)  
  
-   [Явные конструкторы](#explicit_constructors)  
  
-   [Конструкторы по умолчанию](#default_constructors)  
  
-   [Конструкторы копии и перемещения](#copy_and_move_constructors)  
  
-   [Явно заданные и удаленные конструкторы](#explicitly_defaulted_and_deleted_constructors)  
  
-   [Конструкторы в производных классах](#constructors_in_derived_classes)  
  
-   [Виртуальные функции в конструкторах](#virtual_functions_in_constructors)  
  
-   [Конструкторы и составные классы](#constructors_in_composite_classes)  
  
-   [Делегирующие конструкторы](#delegating_constructors)  
  
-   [Наследование конструкторов (C ++ 11)](#inheriting_constructors)  
  
-   [Правила объявления конструкторов](#rules_for_declaring_constructors)  
  
-   [Явно вызываемые конструкторы](#explicitly_invoking_constructors)  
  
##  <a name="order_of_construction"></a>Порядок создания  
 Конструктор выполняет свою работу в следующем порядке.  
  
1.  Вызывает конструкторы базовых классов и членов в порядке объявления.  
  
2.  Если класс является производным от виртуальных базовых классов, конструктор инициализирует указатели виртуальных базовых классов объекта.  
  
3.  Если класс имеет или наследует виртуальные функции, конструктор инициализирует указатели виртуальных функций объекта. Указатели виртуальных функций указывают на таблицу виртуальных функций класса, чтобы обеспечить правильную привязку вызовов виртуальных функций к коду.  
  
4.  Выполняет весь код в теле функции.  
  
 В следующем примере показан порядок, в котором конструкторы базовых классов и конструкторы-члены вызываются в конструкторе производного класса. Сначала вызывается конструктор базового класса, затем инициализируются члены базового класса в порядке их появления в объявлении класса. После этого вызывается конструктор производного класса.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
class Contained1 {  
public:  
    Contained1() {  
        cout << "Contained1 constructor." << endl;  
    }  
};  
  
class Contained2 {  
public:  
    Contained2() {  
        cout << "Contained2 constructor." << endl;  
    }  
};  
  
class Contained3 {  
public:  
    Contained3() {  
        cout << "Contained3 constructor." << endl;  
    }  
};  
  
class BaseContainer {  
public:  
    BaseContainer() {  
        cout << "BaseContainer constructor." << endl;  
    }  
private:  
    Contained1 c1;  
    Contained2 c2;  
};  
  
class DerivedContainer : public BaseContainer {  
public:  
    DerivedContainer() : BaseContainer() {  
        cout << "DerivedContainer constructor." << endl;  
    }  
private:  
    Contained3 c3;  
};  
  
int main() {  
    DerivedContainer dc;  
    int x = 3;  
}  
  
```  
  
 Выходные данные этого кода:  
  
```  
Contained1 constructor.  
Contained2 constructor.  
BaseContainer constructor.  
Contained3 constructor.  
DerivedContainer constructor.  
```  
  
 Если конструктор создает исключение, то удаление выполняется в порядке, обратном созданию.  
  
1.  Отменяется код в теле функции конструктора.  
  
2.  Объекты базовых классов и объекты-члены удаляются в порядке, обратном объявлению.  
  
3.  Если конструктор не является делегирующим, удаляются все полностью созданные объекты базовых классов и объекты-члены. Однако поскольку сам объект создан не полностью, деструктор не вызывается.  
  
##  <a name="member_lists"></a>Списки членов  
 Инициализируйте члены класса из аргументов конструктора, используя список инициализации членов. Этот метод использует *прямой инициализации*, является более эффективным, чем использование операторов присваивания в теле конструктора.  
  
```cpp  
class Box {  
public:  
    Box(int width, int length, int height)   
        : m_width(width), m_length(length), m_height(height) // member init list  
    {}  
    int Volume() {return m_width * m_length * m_height; }  
private:  
    int m_width;  
    int m_length;  
    int m_height;  
  
};  
  
```  
  
 Создание объекта Box:  
  
```  
Box b(42, 21, 12);  
cout << "The volume is " << b.Volume();  
```  
  
##  <a name="explicit_constructors"></a>Явные конструкторы  
 Если у класса имеется конструктор с одним параметром, или у всех параметров, кроме одного, имеются значения по умолчанию, тип параметра можно неявно преобразовать в тип класса. Например, если у класса `Box` имеется конструктор, подобный следующему:  
  
```  
Box(int size): m_width(size), m_length(size), m_height(size){}  
```  
  
 то возможно инициализировать объект Box следующим образом:  
  
```  
Box b = 42;  
```  
  
 Или передать целое значение функции, принимающей объект Box:  
  
```  
class ShippingOrder  
{  
public:  
    ShippingOrder(Box b, double postage) : m_box(b), m_postage(postage){}  
  
private:  
    Box m_box;  
    double m_postage;  
}  
//elsewhere...  
    ShippingOrder so(42, 10.8);  
  
```  
  
 В некоторых случаях подобные преобразования могут быть полезны, однако чаще всего они могут привести к незаметным, но серьезным ошибкам в вашем коде. Как правило, для конструктора (и пользовательских операторов) следует использовать ключевое слово `explicit`, чтобы избежать подобных неявных преобразований типа:  
  
```  
  
explicit Box(int size): m_width(size), m_length(size), m_height(size){}  
```  
  
 Когда конструктор является явным, эта строка вызывает ошибку компилятора: `ShippingOrder so(42, 10.8);`.  Дополнительные сведения см. в разделе [преобразования определяемого пользователем типа](../cpp/user-defined-type-conversions-cpp.md).  
  
##  <a name="default_constructors"></a>Конструкторы по умолчанию  
 *Конструкторы по умолчанию* не имеют параметров подчиняются несколько иным правилам:  
  
 Конструкторы по умолчанию — это одна из *специальные функции-члены*; Если не объявлены конструкторы в классе, компилятор предоставляет конструктор по умолчанию:  
  
```cpp  
class Box {  
    Box(int width, int length, int height)   
        : m_width(width), m_length(length), m_height(height){}  
};  
  
int main(){  
  
    Box box1{}; // call compiler-generated default ctor  
    Box box2;   // call compiler-generated default ctor  
}  
```  
  
 Если при вызове конструктора по умолчанию вы пытаетесь использовать скобки, выводится предупреждение:  
  
```cpp  
class myclass{};  
int main(){  
myclass mc();     // warning C4930: prototyped function not called (was a variable definition intended?)  
}  
```  
  
 Это пример проблемы Most Vexing Parse (наиболее неоднозначного анализа). Поскольку выражение примера можно интерпретировать как объявление функции или как вызов конструктора по умолчанию и в связи с тем, что средства синтаксического анализа C++ отдают предпочтение объявлениям перед другими действиями, данное выражение обрабатывается как объявление функции. Дополнительные сведения см. в разделе [наиболее Vexing Parse](http://en.wikipedia.org/wiki/Most_vexing_parse).  
  
 В случае явного объявления конструкторов компилятор не предоставляет конструктор по умолчанию:  
  
```cpp  
class Box {  
    Box(int width, int length, int height)   
        : m_width(width), m_length(length), m_height(height){}  
};  
private:  
    int m_width;  
    int m_length;  
    int m_height;  
  
};  
  
int main(){  
  
    Box box1(1, 2, 3);  
    Box box2{ 2, 3, 4 };  
    Box box4;     // compiler error C2512: no appropriate default constructor available  
}  
  
```  
  
 Если у класса нет конструктора по умолчанию, массив объектов этого класса не может быть создан только с помощью синтаксиса двух квадратных скобок. Например, в представленном выше блоке кода массив Boxes не может быть объявлен следующим образом:  
  
```cpp  
Box boxes[3];    // compiler error C2512: no appropriate default constructor available  
  
```  
  
 Однако для инициализации массива Boxes можно использовать набор списков инициализаторов:  
  
```cpp  
Box boxes[3]{ { 1, 2, 3 }, { 4, 5, 6 }, { 7, 8, 9 } };  
```  
  
##  <a name="copy_and_move_constructors"></a>Конструкторы копии и перемещения  
 Объект *конструктор копии* имеет специальную функцию-член, принимающую в качестве входных данных ссылку на объект того же типа и создающая его копию. Дополнительные сведения см. в разделе [конструкторы копий и операторы присваивания копирования (C++)](../cpp/copy-constructors-and-copy-assignment-operators-cpp.md). Объект *конструктор перемещения* также имеет специальную функцию-член, перемещает права владения данными существующий объект в новой переменной без копирования исходных данных. Дополнительные сведения см. в разделе [конструкторы перемещения и операторы присваивания перемещения (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md).  
  
##  <a name="explicitly_defaulted_and_deleted_constructors"></a>Явно заданные и удаленные конструкторы  
 Можно явно *по умолчанию* конструкторы копии, конструкторы по умолчанию, конструкторы перемещения, операторы присваивания копий, перемещения, операторы присваивания и деструкторы. Можно явно *удалить* все специальные функции-члены. Дополнительные сведения см. в разделе [явно установленные по умолчанию и удаленные функции](../cpp/explicitly-defaulted-and-deleted-functions.md).  
  
##  <a name="constructors_in_derived_classes"></a>Конструкторы в производных классах  
 Конструктор производного класса всегда вызывает конструктор базового класса, чтобы перед выполнением любых дополнительных операций иметь в своем распоряжении полностью созданные базовые классы. Конструкторы базовых классов вызываются в порядке наследования — например, если ClassA является производным от ClassB, который является производным от ClassC, сначала вызывается конструктор ClassC, затем конструктор ClassB и последним конструктор ClassA.  
  
 Если базовый класс не имеет конструктор по умолчанию, в конструкторе производного класса необходимо указать параметры конструктора базового класса.  
  
```cpp  
class Box {  
public:  
    Box(int width, int length, int height){  
       m_width = width;  
       m_length = length;  
       m_height = height;  
    }  
  
private:  
    int m_width;  
    int m_length;  
    int m_height;  
};  
  
class StorageBox : public Box {  
public:  
    StorageBox(int width, int length, int height, const string label&) : Box(width, length, height){  
        m_label = label;  
    }  
private:  
    string m_label;  
};  
  
int main(){  
  
    const string aLabel = "aLabel";  
    StorageBox sb(1, 2, 3, aLabel);  
}   
```  
  
### <a name="constructors-for-classes-that-have-multiple-inheritance"></a>Конструкторы классов с множественным наследованием  
 Если класс является производным от нескольких базовых классов, конструкторы базовых классов вызываются в том порядке, в котором они перечислены в объявлении производного класса.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
class BaseClass1 {  
public:  
    BaseClass1() {  
        cout << "BaseClass1 constructor." << endl;  
    }  
};  
class BaseClass2 {  
public:  
    BaseClass2() {  
        cout << "BaseClass2 constructor." << endl;  
    }  
};  
class BaseClass3{  
public:  
    BaseClass3() {  
        cout << "BaseClass3 constructor." << endl;  
    }  
};  
class DerivedClass : public BaseClass1, public BaseClass2, public BaseClass3  {  
public:  
    DerivedClass() {  
        cout << "DerivedClass constructor." << endl;  
    }  
};  
  
int main() {  
    DerivedClass dc;  
}  
  
```  
  
 Должны выводиться следующие выходные данные:  
  
```  
BaseClass1 constructor.  
BaseClass2 constructor.  
BaseClass3 constructor.  
DerivedClass constructor.  
```  
  
##  <a name="virtual_functions_in_constructors"></a>Виртуальные функции в конструкторах  
 Рекомендуется соблюдать осторожность при вызове виртуальных функций в конструкторах. Поскольку конструктор базового класса всегда вызывается перед конструктором производного класса, функция, вызываемая в конструкторе базового класса, является версией базового, а не производного класса. В следующем примере создание объекта `DerivedClass` приводит к выполнению реализации объекта `BaseClass` функции `print_it()` перед тем, как конструктор `DerivedClass` вызовет выполнение реализации `DerivedClass` `print_it()`:  
  
```cpp  
#include <iostream>  
using namespace std;  
  
class BaseClass{  
public:  
    BaseClass(){  
        print_it();  
    }  
    virtual void print_it() {  
        cout << "BaseClass print_it" << endl;  
    }  
};  
  
class DerivedClass : public BaseClass {  
public:  
    DerivedClass() {  
        print_it();  
    }  
    virtual void print_it(){  
        cout << "Derived Class print_it" << endl;  
    }  
};  
  
int main() {  
  
    DerivedClass dc;  
}  
```  
  
 Выходные данные этого кода:  
  
```  
BaseClass print_it  
Derived Class print_it  
```  
  
##  <a name="constructors_in_composite_classes"></a>Конструкторы и составные классы  
 Классы, содержащие члены типа класса, называются *составные классы*. При создании члена типа класса составного класса конструктор вызывается перед собственным конструктором класса. Если у содержащегося класса нет конструктора по умолчанию, необходимо использовать список инициализации в конструкторе составного класса. В предыдущем примере `StorageBox` при присвоении типу переменной-члена `m_label` нового класса `Label` необходимо вызвать конструктор базового класса и инициализировать переменную `m_label` в конструкторе `StorageBox`:  
  
```cpp  
class Label {  
public:  
    Label(const string& name, const string& address) { m_name = name; m_address = address; }  
    string m_name;  
    string m_address;  
};  
  
class StorageBox : public Box {  
public:  
    StorageBox(int width, int length, int height, Label label)   
        : Box(width, length, height), m_label(label){}  
private:  
    Label m_label;  
};  
  
int main(){  
// passing a named Label  
    Label label1{ "some_name", "some_address" };  
    StorageBox sb1(1, 2, 3, label1);  
  
    // passing a temporary label  
    StorageBox sb2(3, 4, 5, Label{ "another name", "another address" });  
  
    // passing a temporary label as an initializer list  
    StorageBox sb3(1, 2, 3, {"myname", "myaddress"});  
}  
```  
  
##  <a name="delegating_constructors"></a>Делегирующие конструкторы  
 Объект *делегирующий конструктор* вызывает другой конструктор в том же классе для выполнения некоторых операций инициализации. В следующем примере производный класс содержит три конструктора: второй конструктор делегирует работу первому, а третий — второму.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
class ConstructorDestructor {  
public:  
    ConstructorDestructor() {  
        cout << "ConstructorDestructor default constructor." << endl;  
    }  
    ConstructorDestructor(int int1) {  
        cout << "ConstructorDestructor constructor with 1 int." << endl;  
    }  
    ConstructorDestructor(int int1, int int2) : ConstructorDestructor(int1) {  
        cout << "ConstructorDestructor constructor with 2 ints." << endl;  
  
        throw exception();  
    }  
    ConstructorDestructor(int int1, int int2, int int3) : ConstructorDestructor(int1, int2) {  
        cout << "ConstructorDestructor constructor with 3 ints." << endl;  
    }  
    ~ConstructorDestructor() {  
        cout << "ConstructorDestructor destructor." << endl;  
    }  
};  
  
int main() {  
    ConstructorDestructor dc(1, 2, 3);  
}  
  
```  
  
 Выходные данные этого кода:  
  
```  
ConstructorDestructor constructor with 1 int.  
ConstructorDestructor constructor with 2 ints.  
ConstructorDestructor constructor with 3 ints.  
```  
  
 Объект, созданный конструкторами, полностью инициализируется сразу после выполнения любого конструктора. `DerivedContainer(int int1)` выполняется успешно, но `DerivedContainer(int int1, int int2)` завершается сбоем, и вызывается деструктор.  
  
```cpp  
class ConstructorDestructor {  
public:  
    ConstructorDestructor() {  
        cout << "ConstructorDestructor default constructor." << endl;  
    }  
    ConstructorDestructor(int int1) {  
        cout << "ConstructorDestructor constructor with 1 int." << endl;  
    }  
    ConstructorDestructor(int int1, int int2) : ConstructorDestructor(int1) {  
        cout << "ConstructorDestructor constructor with 2 ints." << endl;  
        throw exception();  
    }  
    ConstructorDestructor(int int1, int int2, int int3) : ConstructorDestructor(int1, int2) {  
        cout << "ConstructorDestructor constructor with 3 ints." << endl;  
    }  
  
    ~ConstructorDestructor() {  
        cout << "ConstructorDestructor destructor." << endl;  
    }  
};  
  
int main() {  
  
    try {  
        ConstructorDestructor cd{ 1, 2, 3 };  
    }  
    catch (const exception& ex){  
    }  
}  
  
```  
  
 Результат  
  
```  
ConstructorDestructor constructor with 1 int.  
ConstructorDestructor constructor with 2 ints.  
ConstructorDestructor destructor.  
```  
  
 Дополнительные сведения см. в разделе [единообразная инициализация и делегирование конструкторов](../cpp/uniform-initialization-and-delegating-constructors.md).  
  
##  <a name="inheriting_constructors"></a>Наследование конструкторов (C ++ 11)  
 Производные классы могут наследовать конструкторы от прямых базовых классов путем объявления using, как показано в следующем примере:  
  
```  
#include <iostream>  
using namespace std;  
  
class Base  
{  
public:      
    Base() { cout << "Base()" << endl; }  
    Base(const Base& other) { cout << "Base(Base&)" << endl; }  
    explicit Base(int i) : num(i) { cout << "Base(int)" << endl; }  
    explicit Base(char c) : letter(c) { cout << "Base(char)" << endl; }  
  
private:  
    int num;  
    char letter;  
};  
  
class Derived : Base  
{  
public:  
    // Inherit all constructors from Base  
    using Base::Base;  
  
private:  
    // Can't initialize newMember from Base constructors.  
    int newMember{ 0 };  
};  
  
int main(int argc, char argv[])  
{  
    cout << "Derived d1(5) calls: ";   
    Derived d1(5);  
    cout << "Derived d1('c') calls: ";  
    Derived d2('c');  
    cout << "Derived d3 = d2 calls: " ;  
    Derived d3 = d2;  
    cout << "Derived d4 calls: ";  
    Derived d4;   
  
    // Keep console open in debug mode:  
    cout << endl << "Press Enter to exit.";  
    char in[1];  
    cin.getline(in, 1);  
    return 0;  
}  
  
/* Output:  
Derived d1(5) calls: Base(int)  
Derived d1('c') calls: Base(char)  
Derived d3 = d2 calls: Base(Base&)  
Derived d4 calls: Base()  
  
Press Enter to exit.  
  
```  
  
 Оператор using переводит в область видимости все конструкторы из базового класса, кроме тех, чьи сигнатуры совпадают с сигнатурами конструкторов из производного класса. Обычно, если в производном классе не объявляются новые данные-члены или конструкторы, оптимальным решением будет использовать наследуемые конструкторы.  
  
 Шаблон класса может наследовать все конструкторы от аргумента типа, если этот тип определяет базовый класс:  
  
```  
template< typename T >  
class Derived : T {  
    using T::T;   // declare the constructors from T  
    // ...  
};  
  
```  
  
 Производный класс не может наследовать от нескольких базовых классов, если у этих базовых классов есть конструкторы с идентичными сигнатурами.  
  
##  <a name="rules_for_declaring_constructors"></a>Правила объявления конструкторов  
 Конструктор имеет то же имя, что и класс. Можно объявить любое количество конструкторов в соответствии с правилами перегруженных функций.  
  
 Список `argument-declaration-list` может быть пустой.  
  
 В C++ определено два специальных типа конструкторов: конструктор по умолчанию и конструктор копии. Они описаны в следующей таблице.  
  
### <a name="default-and-copy-constructors"></a>Конструктор по умолчанию и конструктор копии  
  
|Тип конструктора|Аргументы|Цель|  
|--------------------------|---------------|-------------|  
|Конструктор по умолчанию|Может вызываться без аргументов|Создание объекта по умолчанию типа класса|  
|Конструктор копии|Может принимать один аргумент ссылки на тот же тип класса|Копирование объектов типа класса|  
  
 Конструкторы по умолчанию могут вызываться без аргументов. Однако конструктор по умолчанию можно объявить со списком аргументов при условии, что все аргументы имеют значения по умолчанию. Аналогично конструкторы копий должны принимать один аргумент ссылки на тот же тип класса. Возможно указание нескольких аргументов при условии, что все последующие аргументы имеют значения по умолчанию.  
  
 Если конструкторы не задаются, компилятор пытается создать конструктор по умолчанию. Если конструктор копии не задается, компилятор пытается создать его. Такие создаваемые компилятором конструкторы считаются открытыми функциями-членами. При определении конструктора копии, первым аргументом которого является объект, а не ссылка, возникает ошибка.  
  
 Созданный компилятором конструктор по умолчанию устанавливает объект (инициализирует vftables и vbtables, как было описано выше) и вызывает конструкторы по умолчанию базовых классов и членов, но не выполняет никаких других действий. Конструкторы базовых классов и конструкторы-члены вызываются, только если они существуют, доступны и однозначны.  
  
 Созданный компилятором конструктор копии настраивает новый объект и выполняет почленное копирование содержимого объекта, который нужно скопировать. Если существуют конструкторы базового класса или конструкторы-члены, они вызываются; в противном случае выполняется побитовое копирование.  
  
 Если все базовые классы и член классы класс `type` имеют конструкторы копий, принимающие **const** аргумент конструктора копии, созданные компилятором принимает один аргумент типа **const** `type` **&**. В противном случае конструктор копии, созданные компилятором принимает один аргумент типа `type`  **&** .  
  
 Можно использовать конструктор для инициализации **const** или `volatile` объект, но сам конструктор не может объявляться как **const** или `volatile`. Является единственным допустимым классом хранения для конструктора **встроенного**; использование другого модификатора класса хранения, включая `__declspec` ключевое слово, с помощью конструктора приводит к ошибке компилятора.  
  
 Соглашение о вызовах stdcall используется для статических функций-членов и глобальных функций, объявленных с **__stdcall** ключевое слово, который не используется переменное число аргументов. При использовании **__stdcall** ключевое слово на нестатический член функции, например в конструкторе, компилятор использует соглашение о вызовах thiscall.»  
  
 Конструкторы базовых классов не наследуются производными классами. Объект типа производного класса создается, начиная с компонентов базового класса, а затем перемещается в компоненты производного класса. Компилятор использует конструктор каждого базового класса в процессе инициализации этой части полного объекта (за исключением случаев виртуального наследования.  
  
##  <a name="explicitly_invoking_constructors"></a>Явно вызываемые конструкторы  
 Конструкторы можно явным образом вызывать в программе, чтобы создавать объекты заданного типа. Например, чтобы создать два объекта `Point`, описывающих концы линий, можно написать следующий код:  
  
```  
DrawLine( Point( 13, 22 ), Point( 87, 91 ) );  
```  
  
 Здесь создаются два объекта типа `Point`, которые затем передаются функции `DrawLine` и уничтожаются в конце выражения (вызова функции).  
  
 Конструктор может явным образом вызываться и в другом контексте: при инициализации.  
  
```  
Point pt = Point( 7, 11 );  
```  
  
 В этом примере объект типа `Point` создается и инициализируется при помощи конструктора, который принимает два аргумента типа `int`.  
  
 Объекты, созданные путем явного вызова конструкторов, как показано в этих двух примерах, не имеют имени и существуют столько же времени, сколько и выражение, в котором они были созданы. Эти вопросы рассматриваются более подробно в [временные объекты](../cpp/temporary-objects.md).  
  
 Обычно можно безопасно вызывать из конструктора любую функцию-член, поскольку объект полностью настроен (виртуальные таблицы инициализированы и т. д.) до выполнения первой строки кода пользователя. Однако потенциально небезопасно, если во время создания или удаления функция-член вызывает виртуальную функцию-член абстрактного базового класса.  
  
 Конструкторы могут вызывать виртуальные функции. При вызове виртуальной функции будет вызвана функция, определенная для собственного класса конструктора (или унаследованная из его базовых классов). В следующем примере показано, что происходит, когда виртуальная функция вызывается из конструктора:  
  
```  
// specl_calling_virtual_functions.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class Base  
{  
public:  
    Base();             // Default constructor.  
    virtual void f();   // Virtual member function.  
};  
  
Base::Base()  
{  
    cout << "Constructing Base sub-object\n";  
    f();                // Call virtual member function  
}                       //  from inside constructor.  
  
void Base::f()  
{  
    cout << "Called Base::f()\n";  
}  
  
class Derived : public Base  
{  
public:  
    Derived();          // Default constructor.  
    void f();           // Implementation of virtual  
};                      //  function f for this class.  
  
Derived::Derived()  
{  
    cout << "Constructing Derived object\n";  
}  
  
void Derived::f()  
{  
    cout << "Called Derived::f()\n";  
}  
  
int main()  
{  
    Derived d;  
}  
```  
  
 При выполнении показанной выше программы объявление `Derived d` вызывает следующую последовательность событий:  
  
1.  Производится вызов конструктора для класса `Derived` (`Derived::Derived`).  
  
2.  Перед выполнением основного кода конструктора класса `Derived` вызывается конструктор для класса `Base` (`Base::Base`).  
  
 Конструктор `Base::Base` вызывает функцию `f`, которая является виртуальной. В обычной ситуации вызывалась бы функция `Derived::f`, поскольку объект `d` имеет тип `Derived`. Так как функция `Base::Base` является конструктором, данный объект пока еще не имеет типа `Derived` и вызывается функция `Base::f`.  
  
