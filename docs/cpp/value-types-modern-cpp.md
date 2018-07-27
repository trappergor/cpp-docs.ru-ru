---
title: Значения типов (современный C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f63bb62c-60da-40d5-ac14-4366608fe260
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7e49c97bca86b8d2debde2f5b132f7dde16998e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32423422"
---
# <a name="value-types-modern-c"></a>Типы значений (современный C++)
Классы C++, по типы значений по умолчанию. В этом разделе Вводный обзор типов значений и проблемы, связанные с их использованием.  
  
## <a name="value-vs-reference-types"></a>Значения и ссылочные типы  
 Как уже указывалось, являются классы C++, типы значений по умолчанию. Они могут быть указаны как ссылочные типы, которые позволяют полиморфизма для поддержки объектно ориентированного программирования. Типы значений иногда просматриваются с точки зрения управления памятью и макетом, ссылочные типы являются о базовых классов и виртуальных функций для полиморфного целей. По умолчанию типы значений являются копируемыми, означающее, что всегда существует конструктор копирования и оператор присваивания копии. Для ссылочных типов, чтобы сделать класс некопируемых (отключить конструктор копирования и оператор присваивания копии) и использовать виртуальный деструктор, который поддерживает их предполагаемого полиморфизм. Типы значений также связаны с содержимым, что, если они копируются, всегда обеспечивает два независимых значения, которые могут быть изменены отдельно. Ссылочные типы, связаны с идентификацией — какой тип объекта является его? По этой причине «ссылочные типы» также называется «полиморфных типов».  
  
 Если действительно требуется тип ссылки по принципу (базовый класс, виртуальные функции), необходимо явно отключить копирования, как показано в `MyRefType` класс в следующем коде.  
  
```cpp  
// cl /EHsc /nologo /W4  
  
class MyRefType {  
private:  
    MyRefType & operator=(const MyRefType &);  
    MyRefType(const MyRefType &);  
public:  
    MyRefType () {}  
};  
  
int main()  
{  
    MyRefType Data1, Data2;  
    // ...  
    Data1 = Data2;  
}  
```  
  
 Компиляция приведенный выше код приведет к возникновению следующей ошибки:  
  
```Output  
test.cpp(15) : error C2248: 'MyRefType::operator =' : cannot access private member declared in class 'MyRefType'  
        meow.cpp(5) : see declaration of 'MyRefType::operator ='  
        meow.cpp(3) : see declaration of 'MyRefType'  
  
```  
  
## <a name="value-types-and-move-efficiency"></a>Типы значений и переместить эффективности  
 Из-за новой копии оптимизации позволяет избежать копирования распределения нагрузки. Например при вставке строки в середине вектор строк, будут существовать без копирования повторное выделение издержек только move - даже если это приводит к рост самого вектора. Это справедливо и для других операций, например выполняя операцию добавить двух очень больших объектов. Как включить эти значения операцию оптимизации? В некоторых компиляторах C++ компилятор включит это для вас неявно, подобно конструкторы копирования автоматически создается компилятором. Однако в Visual C++, класс должен «участником» для перемещения назначения и конструкторы, объявив его в определении класса. Это достигается с помощью двойной амперсанд (& &) ссылка rvalue в соответствующий член функции объявления и определение конструктор перемещения и перемещение способы назначения.  Также необходимо вставить правильный код для «кражи внутренностях» из исходного объекта.  
  
 Выбор варианта, если требуется переместить включено? Если уже известно, что требуется скопировать построения включена, возможно, необходимо переместить включена, если может быть дешевле, чем глубокой копией. Тем не менее если известно, что требуется переместить поддержки, он не обязательно означает, что вы хотите включить копию. Последний случай называется «тип только для перемещения». Пример уже в стандартной библиотеке — `unique_ptr`. Заметим, старый `auto_ptr` устарела и была заменена `unique_ptr` точно из-за отсутствия поддержки семантики перемещения в предыдущей версии C++.  
  
 С помощью семантики перемещения возврата по значению или можно вставить в середине. Перемещение — это оптимизация копии. Это потребность в выделение кучи в качестве обходного пути. Рассмотрим следующий псевдокод:  
  
```cpp  
#include <set>  
#include <vector>  
#include <string>  
using namespace std;  
  
//...  
set<widget> LoadHugeData() {  
    set<widget> ret;  
    // ... load data from disk and populate ret  
    return ret;  
}  
//...  
widgets = LoadHugeData();   // efficient, no deep copy  
  
vector<string> v = IfIHadAMillionStrings();  
v.insert( begin(v)+v.size()/2, "scott" );   // efficient, no deep copy-shuffle  
v.insert( begin(v)+v.size()/2, "Andrei" );  // (just 1M ptr/len assignments)  
//...  
HugeMatrix operator+(const HugeMatrix& , const HugeMatrix& );  
HugeMatrix operator+(const HugeMatrix& ,       HugeMatrix&&);  
HugeMatrix operator+(      HugeMatrix&&, const HugeMatrix& );  
HugeMatrix operator+(      HugeMatrix&&,       HugeMatrix&&);  
//...  
hm5 = hm1+hm2+hm3+hm4+hm5;   // efficient, no extra copies  
```  
  
### <a name="enabling-move-for-appropriate-value-types"></a>Включение перемещения для типов соответствующее значение  
 Значение типа класса, где перемещения может быть дешевле, чем глубокой копией включите конструкции перемещения и перемещение назначения для повышения эффективности. Рассмотрим следующий псевдокод:  
  
```cpp  
#include <memory>  
#include <stdexcept>  
using namespace std;  
// ...  
class my_class {  
    unique_ptr<BigHugeData> data;  
public:  
    my_class( my_class&& other )   // move construction  
        : data( move( other.data ) ) { }  
    my_class& operator=( my_class&& other )   // move assignment  
    { data = move( other.data ); return *this; }  
    // ...  
    void method() {   // check (if appropriate)  
        if( !data )   
            throw std::runtime_error("RUNTIME ERROR: Insufficient resources!");  
    }  
};  
  
```  
  
 При включении конструкции копирования и присваивания, также включает конструкции перемещения и присваивания, если он может быть дешевле, чем глубокой копией.  
  
 Некоторые *незначимый* типы, доступные только для перемещения, например, когда не удается клонировать ресурс только Передача владения. Пример: `unique_ptr`.  
  
## <a name="section"></a>Раздел  
 Content  
  
## <a name="see-also"></a>См. также  
 [Тип системы C++](../cpp/cpp-type-system-modern-cpp.md)   
 [Возвращение к C++](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [Справочник по языку C++](../cpp/cpp-language-reference.md)   
 [Стандартная библиотека C++](../standard-library/cpp-standard-library-reference.md)