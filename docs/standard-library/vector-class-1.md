---
title: "вектор Class 1 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::vector"
  - "vector"
  - "std.vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vector - класс"
ms.assetid: a3e0a8f8-7565-4fe0-93e4-e4d74ae1b70d
caps.latest.revision: 24
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# вектор Class 1
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс векторов STL — это класс шаблона контейнеров последовательностей для хранения элементов заданного типа в линейном порядке и быстрого произвольного доступа к любому элементу. Он является наиболее подходящим типом контейнера для последовательности, когда на первом месте стоит производительность произвольного доступа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class Type, class Allocator = allocator<Type>>  
class vector  
```  
  
#### <a name="parameters"></a>Параметры  
 *Тип*  
 Тип данных элементов, сохраняемых в векторе.  
  
 `Allocator`  
 Тип, представляющий сохраненный объект распределителя, содержащий сведения о распределении и отмене распределения памяти для вектора. Этот аргумент является необязательным и значение по умолчанию — **распределителя***\< тип>.*  
  
## <a name="remarks"></a>Примечания  
 Для векторов время выполнения вставок и удалений элементов в конце последовательности является постоянной величиной. Время вставки и удаления элементов в середине вектора меняется линейно. Производительность [класс deque](../standard-library/deque-class.md) контейнера предпочтителен, вставке и удалении элементов в начале и в конце последовательности.  [Класс list](../standard-library/list-class.md) контейнера выше вставок и удалений в любом месте последовательности.  
  
 Расширение вектора происходит, когда функции-члену требуется увеличить последовательность в объекте вектора сверх его текущей емкости. Другие операции вставки и стирания могут изменять различные адреса хранения внутри последовательности. Во всех таких случаях итераторы или ссылки, указывающие на изменившиеся части последовательности, становятся недействительными. Если расширения не происходит, действительными остаются только итераторы и ссылки перед точкой вставки или удаления.  
  
  [Vector \< bool> класс](../Topic/vector%3Cbool%3E%20Class.md) — это полная специализация вектора шаблонного класса для элементов типа bool с распределителем для базового типа, используемого специализацией.  
  
  [Vector \< bool> ссылаться на класс](../Topic/vector%3Cbool%3E%20Class.md#vector_lt_bool_gt___reference_class) — это вложенный класс, объекты которого могут предоставлять ссылки на элементы (отдельные биты) внутри объекта vector \< bool> объекта.  
  
## <a name="members"></a>Члены  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[вектор](#vector__vector)|Создает вектор определенного размера, вектор с элементами определенного значения, вектор с определенным `allocator`, или вектор как копию какого-либо другого вектора.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[allocator_type](#vector__allocator_type)|Тип, представляющий класс `allocator` для объекта вектора.|  
|[const_iterator](#vector__const_iterator)|Тип, предоставляющий итератор произвольного доступа, который может читать элемент `const` в векторе.|  
|[const_pointer](#vector__const_pointer)|Тип, предоставляющий указатель на элемент `const` в векторе.|  
|[const_reference](#vector__const_reference)|Тип, предоставляющий ссылку на элемент `const`, сохраненный в векторе для чтения и выполнения операций `const`.|  
|[const_reverse_iterator](#vector__const_reverse_iterator)|Тип, предоставляющий итератор произвольного доступа, который может читать любой элемент `const` в векторе.|  
|[difference_type](#vector__difference_type)|Тип, представляющий различие между адресами двух элементов в векторе.|  
|[итератор](#vector__iterator)|Тип, предоставляющий итератор произвольного доступа, который может читать или изменять любой элемент в векторе.|  
|[указатель](#vector__pointer)|Тип, предоставляющий указатель на элемент в векторе.|  
|[ссылка](#vector__reference)|Тип, предоставляющий ссылку на элемент, хранящийся в векторе.|  
|[Обратный итератор](#vector__reverse_iterator)|Тип, предоставляющий итератор произвольного доступа, который может читать или изменять любой элемент в обратном векторе.|  
|[size_type](#vector__size_type)|Тип, считающий количество элементов в векторе.|  
|[value_type](#vector__value_type)|Тип, представляющий тип данных, хранящихся в векторе.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[Назначение](#vector__assign)|Удаляет вектор и копирует указанные элементы в пустой вектор.|  
|[в](#vector__at)|Возвращает ссылку на элемент в заданном положении в векторе.|  
|[Назад](#vector__back)|Возвращает ссылку на последний элемент вектора.|  
|[начать](#vector__begin)|Возвращает итератор произвольного доступа, указывающий на первый элемент в векторе.|  
|[емкость](#vector__capacity)|Возвращает число элементов, которое вектор может содержать без выделения дополнительного пространства.|  
|[cbegin](#vector__cbegin)|Возвращает постоянный итератор произвольного доступа, указывающий на первый элемент в векторе.|  
|[cend](#vector__cend)|Возвращает константный итератор произвольного доступа, указывающий на позицию, следующую за концом вектора.|  
|[crbegin](#vector__crbegin)|Возвращает константный итератор, который указывает на первый элемент в обратном векторе.|  
|[crend](#vector__crend)|Возвращает константный итератор, который указывает на последний элемент в обратном векторе.|  
|[Очистка](#vector__clear)|Очищает элементы вектора.|  
|[данные](#vector__data)|Возвращает указатель на первый элемент в векторе.|  
|[emplace](#vector__emplace)|Вставляет элемент, созданный на месте, в указанное положение в векторе.|  
|[emplace_back](#vector__emplace_back)|Добавляет элемент, созданный на месте, в конец вектора.|  
|[пустой](#vector__empty)|Проверяет, пуст ли контейнер вектора.|  
|[конец](#vector__end)|Возвращает итератор произвольного доступа, который указывает на конец вектора.|  
|[Стирание](#vector__erase)|Удаляет элемент или диапазон элементов в векторе из заданных позиций.|  
|[передний план](#vector__front)|Возвращает ссылку на первый элемент в векторе.|  
|[get_allocator](#vector__get_allocator)|Возвращает объект классу `allocator`, используемому вектором.|  
|[Вставка](#vector__insert)|Вставляет элемент или некоторое число элементов в вектор в заданной позиции.|  
|[max_size](#vector__max_size)|Возвращает максимальную длину вектора.|  
|[pop_back](#vector__pop_back)|Удаляет элемент в конце вектора.|  
|[push_back](#vector__push_back)|Добавляет элемент в конец вектора.|  
|[rbegin](#vector__rbegin)|Возвращает итератор, указывающий на первый элемент в обратном векторе.|  
|[rend](#vector__rend)|Возвращает итератор, который указывает на последний элемент в обратном векторе.|  
|[Резерв](#vector__reserve)|Резервирует минимальную длину хранилища для объекта вектора.|  
|[Изменение размеров](#vector__resize)|Определяет новый размер вектора.|  
|[shrink_to_fit](#vector__shrink_to_fit)|Удаляет лишнюю емкость.|  
|[размер](#vector__size)|Возвращает количество элементов в векторе.|  
|[Переключение](#vector__swap)|Меняет местами элементы двух векторов.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор &#91; &#93;](#vector__operator_at)|Возвращает ссылку на элемент вектора в указанной позиции.|  
|[оператор =](#vector__operator_eq)|Заменяет элементы вектора копией другого вектора.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \< vector>  
  
 **Пространство имен:** std  
  
##  <a name="a-namevectorallocatortypea-vectorallocatortype"></a><a name="vector__allocator_type"></a>  Vector::allocator_type  
 Тип, представляющий класс распределителя для объекта вектора.  
  
```  
typedef Allocator allocator_type;  
```  
  
### <a name="remarks"></a>Примечания  
 `allocator_type` является синонимом параметра шаблона **распределителя.**  
  
### <a name="example"></a>Пример  
  В примере показано [get_allocator](#vector__get_allocator) пример, использующий `allocator_type`.  
  
##  <a name="a-namevectorassigna-vectorassign"></a><a name="vector__assign"></a>  Vector::Assign  
 Удаляет вектор и копирует указанные элементы в пустой вектор.  
  
```  
void assign(
    size_type Count,  
    const Type& Val);

void assign(
    initializer_list<Type> IList);

template <class InputIterator>  
void assign(
    InputIterator First,  
    InputIterator Last);
```  
  
### <a name="parameters"></a>Параметры  
 `First`  
 Положение первого элемента в диапазоне копируемых элементов.  
  
 `Last`  
 Положение первого элемента за пределами диапазона копируемых элементов.  
  
 `Count`  
 Количество копий элемента, вставляемых в вектор.  
  
 `Val`  
 Значение элемента, вставляемого в вектор.  
  
 `IList`  
 Объект initializer_list, содержащий вставляемые элементы.  
  
### <a name="remarks"></a>Примечания  
 После очистки существующих элементов в векторе функция assign вставляет в вектор либо указанный диапазон элементов из исходного вектора, либо копии нового элемента с указанным значением.  
  
### <a name="example"></a>Пример  
  
```  
/ vector_assign.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    vector<int> v1, v2, v3;  
  
    v1.push_back(10);  
    v1.push_back(20);  
    v1.push_back(30);  
    v1.push_back(40);  
    v1.push_back(50);  
  
    cout << "v1 = ";  
    for (auto& v : v1){  
        cout << v << " ";  
    }  
    cout << endl;  
  
    v2.assign(v1.begin(), v1.end());  
    cout << "v2 = ";  
    for (auto& v : v2){  
        cout << v << " ";  
    }  
    cout << endl;  
  
    v3.assign(7, 4);  
    cout << "v3 = ";  
    for (auto& v : v3){  
        cout << v << " ";  
    }  
    cout << endl;  
  
    v3.assign({ 5, 6, 7 });  
    for (auto& v : v3){  
        cout << v << " ";  
    }  
    cout << endl;  
}  
  
```  
  
##  <a name="a-namevectorata-vectorat"></a><a name="vector__at"></a>  Vector::AT  
 Возвращает ссылку на элемент в заданном положении в векторе.  
  
```  
reference at(size_type _Pos);

const_reference at(size_type _Pos) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Pos`  
 Номер нижнего индекса или позиции элемента, на который включается ссылка в векторе.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на элемент, индекс которого указан в аргументе. Если `_Off` больше размера вектора, **в** приводит к возникновению исключения.  
  
### <a name="remarks"></a>Примечания  
 Если возвращаемое значение **в** назначается `const_reference`, то объект вектора нельзя изменить. Если возвращаемое значение **в** назначается **ссылки**, то объект вектора можно изменить.  
  
### <a name="example"></a>Пример  
  
```  
// vector_at.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector <int> v1;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
  
   const int &i = v1.at( 0 );  
   int &j = v1.at( 1 );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="a-namevectorbacka-vectorback"></a><a name="vector__back"></a>  Vector::Back  
 Возвращает ссылку на последний элемент вектора.  
  
```  
reference back();

const_reference back() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Последний элемент вектора. Если вектор пуст, возвращаемое значение не определено.  
  
### <a name="remarks"></a>Примечания  
 Если возвращаемое значение **обратно** назначается `const_reference`, то объект вектора нельзя изменить. Если возвращаемое значение **обратно** назначается **ссылки**, то объект вектора можно изменить.  
  
 При компиляции с параметром _SECURE_SCL 1 возникнет ошибка времени выполнения при попытке доступа к элементу в пустом векторе.  Дополнительные сведения см. в разделе [Checked Iterators](../standard-library/checked-iterators.md) .  
  
### <a name="example"></a>Пример  
  
```  
// vector_back.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main() {  
   using namespace std;     
   vector <int> v1;  
  
   v1.push_back( 10 );  
   v1.push_back( 11 );  
  
   int& i = v1.back( );  
   const int& ii = v1.front( );  
  
   cout << "The last integer of v1 is " << i << endl;  
   i--;  
   cout << "The next-to-last integer of v1 is "<< ii << endl;  
}  
```  
  
##  <a name="a-namevectorbegina-vectorbegin"></a><a name="vector__begin"></a>  Vector::BEGIN  
 Возвращает итератор произвольного доступа, указывающий на первый элемент в векторе.  
  
```  
const_iterator begin() const;

 
iterator begin();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор произвольного доступа, обращающийся к первому элементу в `vector` или расположение после пустого `vector`. Всегда следует сравнивать значения, возвращаемого с [vector::end](#vector__end) для проверки его действительности.  
  
### <a name="remarks"></a>Примечания  
 Если возвращаемое значение `begin` назначается [vector::const_iterator](#vector__const_iterator),  `vector` объект не может быть изменен. Если возвращаемое значение `begin` назначается [vector::iterator](#vector__iterator),  `vector` объект может быть изменен.  
  
### <a name="example"></a>Пример  
  
```  
// vector_begin.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    vector<int> c1;  
    vector<int>::iterator c1_Iter;  
    vector<int>::const_iterator c1_cIter;  
  
    c1.push_back(1);  
    c1.push_back(2);  
  
    cout << "The vector c1 contains elements:";  
    c1_Iter = c1.begin();  
    for (; c1_Iter != c1.end(); c1_Iter++)  
    {  
        cout << " " << *c1_Iter;  
    }  
    cout << endl;  
  
    cout << "The vector c1 now contains elements:";  
    c1_Iter = c1.begin();  
 *c1_Iter = 20;  
    for (; c1_Iter != c1.end(); c1_Iter++)  
    {  
        cout << " " << *c1_Iter;  
    }  
    cout << endl;  
  
    // The following line would be an error because iterator is const  
    // *c1_cIter = 200;  
}  
```  
  
```Output  
The vector c1 contains elements: 1 2  
The vector c1 now contains elements: 20 2  
```  
  
##  <a name="a-namevectorcapacitya-vectorcapacity"></a><a name="vector__capacity"></a>  Vector::Capacity  
 Возвращает число элементов, которое вектор может содержать без выделения дополнительного пространства.  
  
```  
size_type capacity() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущая длина хранилища, выделенного вектору.  
  
### <a name="remarks"></a>Примечания  
 Функция-член [изменения размера](#vector__resize) будет более эффективным, если для нее выделено достаточно памяти. Используйте функцию-член [зарезервировать](#vector__reserve) Указывает объем выделенной памяти.  
  
### <a name="example"></a>Пример  
  
```  
// vector_capacity.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector <int> v1;  
  
   v1.push_back( 1 );  
   cout << "The length of storage allocated is "  
        << v1.capacity( ) << "." << endl;  
  
   v1.push_back( 2 );  
   cout << "The length of storage allocated is now "  
        << v1.capacity( ) << "." << endl;  
}  
```  
  
```Output  
The length of storage allocated is 1.  
The length of storage allocated is now 2.  
```  
  
##  <a name="a-namevectorcbegina-vectorcbegin"></a><a name="vector__cbegin"></a>  Vector::cbegin  
 Возвращает итератор `const`, направленный на первый элемент в диапазоне.  
  
```  
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор случайного доступа `const`, который указывает на первый элемент диапазона или расположение прямо за концом пустого диапазона (`cbegin() == cend()` для пустого диапазона).  
  
### <a name="remarks"></a>Примечания  
 Элементы в диапазоне нельзя изменить с помощью возвращаемого значения `cbegin`.  
  
 Эту функцию-член можно использовать вместо функции-члена `begin()`, чтобы гарантировать, что возвращаемое значение будет `const_iterator`. Как правило, он используется в сочетании с [автоматически](../cpp/auto-cpp.md) ключевым словом вывода, типа, как показано в следующем примере. В примере рассмотрим `Container` является изменяемым (отличного от `const`) контейнер для любого типа, который поддерживает `begin()` и `cbegin()`.  
  
```cpp  
 
auto i1 = Container.begin();
// i1 is Container<T>::iterator   
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator  
```  
  
##  <a name="a-namevectorcenda-vectorcend"></a><a name="vector__cend"></a>  Vector::cend  
 Возвращает итератор `const`, который обращается к месту, следующему сразу за последним элементом в диапазоне.  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор `const` с произвольным доступом, который указывает конец диапазона.  
  
### <a name="remarks"></a>Примечания  
 `cend` используется для проверки того, прошел ли итератор конец диапазона.  
  
 Эту функцию-член можно использовать вместо функции-члена `end()`, чтобы гарантировать, что возвращаемое значение будет `const_iterator`. Как правило, он используется в сочетании с [автоматически](../cpp/auto-cpp.md) ключевым словом вывода, типа, как показано в следующем примере. В примере рассмотрим `Container` является изменяемым (отличного от `const`) контейнер для любого типа, который поддерживает `end()` и `cend()`.  
  
```cpp  
 
auto i1 = Container.end();
// i1 is Container<T>::iterator   
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator  
```  
  
 Значение, возвращаемое `cend`, не должно быть подвергнуто удалению ссылки.  
  
##  <a name="a-namevectorcleara-vectorclear"></a><a name="vector__clear"></a>  Vector::Clear  
 Очищает элементы вектора.  
  
```  
void clear();
```  
  
### <a name="example"></a>Пример  
  
```  
// vector_clear.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
   v1.push_back( 30 );  
  
   cout << "The size of v1 is " << v1.size( ) << endl;  
   v1.clear( );  
   cout << "The size of v1 after clearing is " << v1.size( ) << endl;  
}  
```  
  
```Output  
The size of v1 is 3  
The size of v1 after clearing is 0  
```  
  
##  <a name="a-namevectorconstiteratora-vectorconstiterator"></a><a name="vector__const_iterator"></a>  Vector::const_iterator  
 Тип, предоставляющий итератор произвольного доступа, который может читать **const** элемент в векторе.  
  
```  
typedef implementation-defined const_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип `const_iterator`нельзя использовать для изменения значения элемента.  
  
### <a name="example"></a>Пример  
  В примере показано [обратно](#vector__back) пример, использующий `const_iterator`.  
  
##  <a name="a-namevectorconstpointera-vectorconstpointer"></a><a name="vector__const_pointer"></a>  Vector::const_pointer  
 Тип, который предоставляет указатель **const** элемент в векторе.  
  
```  
typedef typename Allocator::const_pointer const_pointer;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип `const_pointer`нельзя использовать для изменения значения элемента.  
  
  [Итератор](#vector__iterator) для доступа к элементу вектора чаще используется.  
  
##  <a name="a-namevectorconstreferencea-vectorconstreference"></a><a name="vector__const_reference"></a>  Vector::const_reference  
 Тип, предоставляющий ссылку на **const** элемент, хранящийся в векторе для чтения и выполнения **const** операций.  
  
```  
typedef typename Allocator::const_reference const_reference;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип `const_reference`нельзя использовать для изменения значения элемента.  
  
### <a name="example"></a>Пример  
  
```  
// vector_const_ref.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector <int> v1;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
  
   const vector <int> v2 = v1;  
   const int &i = v2.front( );  
   const int &j = v2.back( );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
  
   // The following line would cause an error as v2 is const  
   // v2.push_back( 30 );  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="a-namevectorconstreverseiteratora-vectorconstreverseiterator"></a><a name="vector__const_reverse_iterator"></a>  Vector::const_reverse_iterator  
 Тип, предоставляющий итератор произвольного доступа, который может читать любой **const** элемент в векторе.  
  
```  
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип `const_reverse_iterator` Невозможно изменить значение элемента и используется для последовательного прохождения через вектор в обратную сторону.  
  
### <a name="example"></a>Пример  
  В разделе [rbegin](#vector__rbegin) пример того, как объявить и использовать итератор.  
  
##  <a name="a-namevectorcrbegina-vectorcrbegin"></a><a name="vector__crbegin"></a>  Vector::crbegin  
 Возвращает константный итератор, который указывает на первый элемент в обратном векторе.  
  
```  
const_reverse_iterator crbegin() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Постоянный Обратный итератор произвольного доступа, обращающийся к первому элементу в обратном [вектор](vector%20Class.md) или решить, что было последним элементом в необращенном `vector`.  
  
### <a name="remarks"></a>Примечания  
 Если возвращаемое значение `crbegin`, то объект `vector` невозможно изменить.  
  
### <a name="example"></a>Пример  
  
```  
// vector_crbegin.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::iterator v1_Iter;  
   vector <int>::const_reverse_iterator v1_rIter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
  
   v1_Iter = v1.begin( );  
   cout << "The first element of vector is "  
        << *v1_Iter << "." << endl;  
  
   v1_rIter = v1.crbegin( );  
   cout << "The first element of the reversed vector is "  
        << *v1_rIter << "." << endl;  
}  
```  
  
```Output  
The first element of vector is 1.  
The first element of the reversed vector is 2.  
```  
  
##  <a name="a-namevectorcrenda-vectorcrend"></a><a name="vector__crend"></a>  Vector::crend  
 Возвращает константный итератор, адресующий расположение после последнего элемента в обратном векторе.  
  
```  
const_reverse_iterator crend() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Постоянный Обратный итератор произвольного доступа, который обращается к месту, следующему за последним элементом в обратном [вектор](vector%20Class.md) (расположение перед первым элементом в необращенном `vector`).  
  
### <a name="remarks"></a>Примечания  
 `crend` используется с обратном `vector` так же, как [vector::cend](#vector__cend) используется с `vector`.  
  
 Возвращаемое значение из `crend` (соответственно уменьшенное), `vector` объект не может быть изменен.  
  
 `crend` используется, чтобы проверить, достиг ли итератор конца `vector`.  
  
 Значение, возвращаемое `crend`, не должно быть подвергнуто удалению ссылки.  
  
### <a name="example"></a>Пример  
  
```  
// vector_crend.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::const_reverse_iterator v1_rIter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
  
   for ( v1_rIter = v1.rbegin( ) ; v1_rIter != v1.rend( ) ; v1_rIter++ )  
      cout << *v1_rIter << endl;  
}  
```  
  
```Output  
2  
1  
```  
  
##  <a name="a-namevectordataa-vectordata"></a><a name="vector__data"></a>  Vector::Data  
 Возвращает указатель на первый элемент в векторе.  
  
```  
const_pointer data() const;

 
pointer data();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на первый элемент в [вектор](vector%20Class.md) или расположение после пустого `vector`.  
  
### <a name="example"></a>Пример  
  
```  
// vector_data.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    vector<int> c1;  
    vector<int>::pointer c1 ptr;  
    vector<int>::const_pointer c1_cPtr;  
  
    c1.push_back(1);  
    c1.push_back(2);  
  
    cout << "The vector c1 contains elements:";  
    c1_cPtr = c1.data();  
    for (size_t n = c1.size(); 0 < n; --n, c1_cPtr++)  
    {  
        cout << " " << *c1_cPtr;  
    }  
    cout << endl;  
  
    cout << "The vector c1 now contains elements:";  
    c1 ptr = c1.data();  
 *c1 ptr = 20;  
    for (size_t n = c1.size(); 0 < n; --n, c1 ptr++)  
    {  
        cout << " " << *c1 ptr;  
    }  
    cout << endl;  
}  
```  
  
```Output  
The vector c1 contains elements: 1 2  
The vector c1 now contains elements: 20 2  
```  
  
##  <a name="a-namevectordifferencetypea-vectordifferencetype"></a><a name="vector__difference_type"></a>  Vector::difference_type  
 Тип, предоставляющий разницу между двумя итераторами, ссылающимися на элементы в одном и том же векторе.  
  
```  
typedef typename Allocator::difference_type difference_type;  
```  
  
### <a name="remarks"></a>Примечания  
 A `difference_type` также можно описать как число элементов между двумя указателями, так как содержит указатель на элемент его адрес.  
  
  [Итератор](#vector__iterator) для доступа к элементу вектора чаще используется.  
  
### <a name="example"></a>Пример  
  
```  
// vector_diff_type.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <vector>  
#include <algorithm>  
  
int main( )  
{  
   using namespace std;  
  
   vector <int> c1;  
   vector <int>::iterator c1_Iter, c2_Iter;  
  
   c1.push_back( 30 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
   c1.push_back( 10 );  
   c1.push_back( 30 );  
   c1.push_back( 20 );  
  
   c1_Iter = c1.begin( );  
   c2_Iter = c1.end( );  
  
   vector <int>::difference_type   df_typ1, df_typ2, df_typ3;  
  
   df_typ1 = count( c1_Iter, c2_Iter, 10 );  
   df_typ2 = count( c1_Iter, c2_Iter, 20 );  
   df_typ3 = count( c1_Iter, c2_Iter, 30 );  
   cout << "The number '10' is in c1 collection " << df_typ1 << " times.\n";  
   cout << "The number '20' is in c1 collection " << df_typ2 << " times.\n";  
   cout << "The number '30' is in c1 collection " << df_typ3 << " times.\n";  
}  
```  
  
```Output  
The number '10' is in c1 collection 1 times.  
The number '20' is in c1 collection 2 times.  
The number '30' is in c1 collection 3 times.  
```  
  
##  <a name="a-namevectoremplacea-vectoremplace"></a><a name="vector__emplace"></a>  Vector::emplace  
 Вставляет элемент, созданный на месте, в указанное положение в векторе.  
  
```  
iterator emplace(
    const_iterator _Where,  
    Type&& val);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`_Where`|Позиция в [вектор](vector%20Class.md) куда вставляется первый элемент.|  
|` val`|Значение элемента, вставляемого в `vector`.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Функция возвращают итератор, указывающий на положение вставки нового элемента в `vector`.  
  
### <a name="remarks"></a>Примечания  
 Любая операция вставки может быть дорогостоящей см. в разделе [класс vector](vector%20Class.md) обсуждение `vector` производительности.  
  
### <a name="example"></a>Пример  
  
```  
// vector_emplace.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::iterator Iter;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
   v1.push_back( 30 );  
  
   cout << "v1 =" ;  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
// initialize a vector of vectors by moving v1  
   vector < vector <int> > vv1;  
  
   vv1.emplace( vv1.begin(), move( v1 ) );  
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )  
      {  
      cout << "vv1[0] =";  
      for (Iter = vv1[0].begin( ); Iter != vv1[0].end( ); Iter++ )  
         cout << " " << *Iter;  
      cout << endl;  
      }  
}  
```  
  
```Output  
v1 = 10 20 30  
vv1[0] = 10 20 30  
```  
  
##  <a name="a-namevectoremplacebacka-vectoremplaceback"></a><a name="vector__emplace_back"></a>  Vector::emplace_back  
 Добавляет элемент, созданный на месте, в конец вектора.  
  
```  
template <class... Types>  
void emplace_back(Types&&... _Args);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`_Args`|Аргументы конструктора. Функция определяет перегрузку конструктора, которую нужно вызвать, на основе переданных аргументов.|  
  
### <a name="example"></a>Пример  
  
```cpp  
  
#include <vector>  
struct obj  
{  
   obj(int, double) {}  
};  
  
int main()  
{  
   std::vector<obj> v;  
   v.emplace_back(1, 3.14); // obj in created in place in the vector  
}  
  
```  
  
##  <a name="a-namevectoremptya-vectorempty"></a><a name="vector__empty"></a>  Vector::Empty  
 Проверяет, если вектор пуст.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если вектор пуст; **false** Если вектор не пуст.  
  
### <a name="example"></a>Пример  
  
```  
// vector_empty.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
  
   v1.push_back( 10 );  
  
   if ( v1.empty( ) )  
      cout << "The vector is empty." << endl;  
   else  
      cout << "The vector is not empty." << endl;  
}  
```  
  
```Output  
The vector is not empty.  
```  
  
##  <a name="a-namevectorenda-vectorend"></a><a name="vector__end"></a>  Vector::End  
 Возврат итератора после конца.  
  
```  
iterator end();

const_iterator end() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор после конца для вектора. Если вектор пуст, то `vector::end() == vector::begin()`.  
  
### <a name="remarks"></a>Примечания  
 Если возвращаемое значение **end** присваивается переменной типа `const_iterator`, то объект вектора нельзя изменить. Если возвращаемое значение **end** присваивается переменной типа **итератор**, то объект вектора можно изменить.  
  
### <a name="example"></a>Пример  
  
```  
// vector_end.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
int main( )  
{  
   using namespace std;  
   vector <int> v1;  
   vector <int>::iterator v1_Iter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
  
   for ( v1_Iter = v1.begin( ) ; v1_Iter != v1.end( ) ; v1_Iter++ )  
      cout << *v1_Iter << endl;  
}  
```  
  
```Output  
1  
2  
```  
  
##  <a name="a-namevectorerasea-vectorerase"></a><a name="vector__erase"></a>  Vector::Erase  
 Удаляет элемент или диапазон элементов в векторе из заданных позиций.  
  
```  
iterator erase(
    const_iterator _Where);

iterator erase(
    const_iterator first,  
    const_iterator last);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`_Where`|Положение элемента, удаляемого из вектора.|  
|` first`|Положение первого элемента, удаляемого из вектора.|  
|` last`|Положение после последнего элемента, удаляемого из вектора.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор, указывающий на первый элемент, оставшийся после удаленных элементов, или на указатель конца вектора, если такого элемента не существует.  
  
### <a name="example"></a>Пример  
  
```  
// vector_erase.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::iterator Iter;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
   v1.push_back( 30 );  
   v1.push_back( 40 );  
   v1.push_back( 50 );  
  
   cout << "v1 =" ;  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
   v1.erase( v1.begin( ) );  
   cout << "v1 =";  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
   v1.erase( v1.begin( ) + 1, v1.begin( ) + 3 );  
   cout << "v1 =";  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
}  
```  
  
```Output  
v1 = 10 20 30 40 50  
v1 = 20 30 40 50  
v1 = 20 50  
```  
  
##  <a name="a-namevectorfronta-vectorfront"></a><a name="vector__front"></a>  Vector::Front  
 Возвращает ссылку на первый элемент в векторе.  
  
```  
reference front();

const_reference front() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на первый элемент в объекте вектора. Если вектор пуст, возвращаемое значение не определено.  
  
### <a name="remarks"></a>Примечания  
 Если возвращаемое значение `front` присвоено `const_reference`, то объект вектора нельзя изменить. Если возвращаемое значение `front` назначается **ссылки**, то объект вектора можно изменить.  
  
 При компиляции с параметром _SECURE_SCL 1 возникнет ошибка времени выполнения при попытке доступа к элементу в пустом векторе.  Дополнительные сведения см. в разделе [Checked Iterators](../standard-library/checked-iterators.md) .  
  
### <a name="example"></a>Пример  
  
```  
// vector_front.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
  
   v1.push_back( 10 );  
   v1.push_back( 11 );  
  
   int& i = v1.front( );  
   const int& ii = v1.front( );  
  
   cout << "The first integer of v1 is "<< i << endl;  
   // by incrementing i, we move the the front reference to the second element  
   i++;  
   cout << "Now, the first integer of v1 is "<< i << endl;  
}  
```  
  
##  <a name="a-namevectorgetallocatora-vectorgetallocator"></a><a name="vector__get_allocator"></a>  Vector::get_allocator  
 Возвращает копию объекта распределителя, использованного для создания объекта vector.  
  
```  
Allocator get_allocator() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Распределитель, используемый вектором.  
  
### <a name="remarks"></a>Примечания  
 Распределители для класса vector определяют, как класс управляет хранилищем. Для большинства задач программирования достаточно распределителей по умолчанию, доступных вместе с классами контейнеров STL. Написание и использование собственного класса распределителя требует расширенных навыков работы с C++.  
  
### <a name="example"></a>Пример  
  
```  
// vector_get_allocator.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   // The following lines declare objects that use the default allocator.  
   vector<int> v1;  
   vector<int, allocator<int> > v2 = vector<int, allocator<int> >(allocator<int>( )) ;  
  
   // v3 will use the same allocator class as v1  
   vector <int> v3( v1.get_allocator( ) );  
  
   vector<int>::allocator_type xvec = v3.get_allocator( );  
   // You can now call functions on the allocator class used by vec  
}  
```  
  
##  <a name="a-namevectorinserta-vectorinsert"></a><a name="vector__insert"></a>  Vector::INSERT  
 Вставляет элемент, определенное количество элементов или диапазон элементов в указанную позицию в векторе.  
  
```  
iterator insert(
    const_iterator _Where,  
    const Type& val);

iterator insert(
    const_iterator _Where,  
    Type&& val);

void insert(
    const_iterator _Where,  
    size_type count,  
    const Type& val);

template <class InputIterator>  
void insert(
    const_iterator _Where,  
    InputIterator first,  
    InputIterator last);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`_Where`|Позиция в векторе, куда вставляется первый элемент.|  
|` val`|Значение элемента, вставляемого в вектор.|  
|` count`|Количество элементов, вставляемых в вектор.|  
|` first`|Положение первого элемента в диапазоне копируемых элементов.|  
|` last`|Положение первого элемента после диапазона копируемых элементов.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Две первые функции `insert` возвращают итератор, указывающий на положение вставки нового элемента в вектор.  
  
### <a name="remarks"></a>Примечания  
 Любая операция вставки может быть дорогостоящей см. в разделе [класс vector](vector%20Class.md) обсуждение `vector` производительности.  
  
### <a name="example"></a>Пример  
  
```  
// vector_insert.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::iterator Iter;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
   v1.push_back( 30 );  
  
   cout << "v1 =" ;  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
   v1.insert( v1.begin( ) + 1, 40 );  
   cout << "v1 =";  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
   v1.insert( v1.begin( ) + 2, 4, 50 );  
  
   cout << "v1 =";  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
   v1.insert( v1.begin( )+1, v1.begin( )+2, v1.begin( )+4 );  
   cout << "v1 =";  
   for (Iter = v1.begin( ); Iter != v1.end( ); Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
// initialize a vector of vectors by moving v1  
   vector < vector <int> > vv1;  
  
   vv1.insert( vv1.begin(), move( v1 ) );  
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )  
      {  
      vector < vector <int> >::iterator Iter;  
      cout << "vv1[0] =";  
      for (Iter = vv1[0].begin( ); Iter != vv1[0].end( ); Iter++ )  
         cout << " " << *Iter;  
      cout << endl;  
      }  
}  
```  
  
```Output  
v1 = 10 20 30  
v1 = 10 40 20 30  
v1 = 10 40 50 50 50 50 20 30  
v1 = 10 50 50 40 50 50 50 50 20 30  
vv1[0] = 10 50 50 40 50 50 50 50 20 30  
```  
  
##  <a name="a-namevectoriteratora-vectoriterator"></a><a name="vector__iterator"></a>  Vector::iterator  
 Тип, предоставляющий итератор произвольного доступа, который может читать или изменять любой элемент в векторе.  
  
```  
typedef implementation-defined iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип **итератор** можно использовать для изменения значения элемента.  
  
### <a name="example"></a>Пример  
  В примере показано [Начать](#vector__begin).  
  
##  <a name="a-namevectormaxsizea-vectormaxsize"></a><a name="vector__max_size"></a>  Vector::max_size  
 Возвращает максимальную длину вектора.  
  
```  
size_type max_size() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимально возможная длина вектора.  
  
### <a name="example"></a>Пример  
  
```  
// vector_max_size.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::size_type i;  
  
   i = v1.max_size( );     
   cout << "The maximum possible length of the vector is " << i << "." << endl;  
}  
```  
  
##  <a name="a-namevectoroperatorata-vectoroperator"></a><a name="vector__operator_at"></a>  Vector::operator]  
 Возвращает ссылку на элемент вектора в указанной позиции.  
  
```  
reference operator[](size_type Pos);

const_reference operator[](size_type Pos) const;
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`Pos`|Позиция элемента вектора.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если заданная позиция больше или равна размеру контейнера, результат не определен.  
  
### <a name="remarks"></a>Примечания  
 Если возвращаемое значение `operator[]` присвоено `const_reference`, то объект вектора нельзя изменить. Если возвращаемое значение `operator[]` присвоено ссылке, то объект вектора можно изменить.  
  
 При компилировании с _SECURE_SCL (контролируется с помощью [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)), возникнет ошибка времени выполнения при попытке доступа к элементу за пределами вектора.  Дополнительные сведения см. в разделе [Checked Iterators](../standard-library/checked-iterators.md) .  
  
### <a name="example"></a>Пример  
  
```cpp  
// vector_op_ref.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
  
   int& i = v1[1];  
   cout << "The second integer of v1 is " << i << endl;  
}  
```  
  
##  <a name="a-namevectoroperatoreqa-vectoroperator"></a><a name="vector__operator_eq"></a>  Vector::operator =  
 Заменяет элементы вектора копией другого вектора.  
  
```  
vector& operator=(const vector& right);

vector& operator=(vector&& right);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|` right`| [Вектор](vector%20Class.md) копируется в `vector`.|  
  
### <a name="remarks"></a>Примечания  
 После удаления всех существующих элементов в объекте `vector` `operator=` копирует или перемещает содержимое ` right` в объект `vector`.  
  
### <a name="example"></a>Пример  
  
```  
// vector_operator_as.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector<int> v1, v2, v3;  
   vector<int>::iterator iter;  
  
   v1.push_back(10);  
   v1.push_back(20);  
   v1.push_back(30);  
   v1.push_back(40);  
   v1.push_back(50);  
  
   cout << "v1 = " ;  
   for (iter = v1.begin(); iter != v1.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
  
   v2 = v1;  
   cout << "v2 = ";  
   for (iter = v2.begin(); iter != v2.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
  
// move v1 into v2  
   v2.clear();  
   v2 = move(v1);  
   cout << "v2 = ";  
   for (iter = v2.begin(); iter != v2.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
}  
```  
  
##  <a name="a-namevectorpointera-vectorpointer"></a><a name="vector__pointer"></a>  Vector::pointer  
 Тип, предоставляющий указатель на элемент в векторе.  
  
```  
typedef typename Allocator::pointer pointer;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип **указатель** можно использовать для изменения значения элемента.  
  
### <a name="example"></a>Пример  
  
```  
// vector_pointer.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector<int> v;  
   v.push_back( 11 );  
   v.push_back( 22 );  
  
   vector<int>::pointer ptr = &v[0];  
   cout << *ptr << endl;  
   ptr++;  
   cout << *ptr << endl;  
 *ptr = 44;  
   cout << *ptr << endl;  
}  
```  
  
```Output  
11  
22  
44  
```  
  
##  <a name="a-namevectorpopbacka-vectorpopback"></a><a name="vector__pop_back"></a>  Vector::pop_back  
 Удаляет элемент в конце вектора.  
  
```  
void pop_back();
```  
  
### <a name="remarks"></a>Примечания  
 Пример кода в разделе [vector:: push_back()](#vector__push_back).  
  
##  <a name="a-namevectorpushbacka-vectorpushback"></a><a name="vector__push_back"></a>  Vector::push_back  
 Добавляет элемент в конец вектора.  
  
```  
void push_back(const T& Val);

 
void push_back(T&& Val);
```  
  
### <a name="parameters"></a>Параметры  
 `Val`  
 Значение, назначаемое элементу, который добавляется в конец вектора.  
  
### <a name="example"></a>Пример  
  
```cpp  
// compile with: /EHsc /W4  
#include <vector>  
#include <iostream>  
  
using namespace std;  
  
template <typename T> void print_elem(const T& t) {  
    cout << "(" << t << ") ";  
}  
  
template <typename T> void print_collection(const T& t) {  
    cout << "  " << t.size() << " elements: ";  
  
    for (const auto& p : t) {  
        print_elem(p);  
    }  
    cout << endl;  
}  
  
int main()  
{  
    vector<int> v;  
    for (int i = 0; i < 10; ++i) {  
        v.push_back(10 + i);  
    }  
  
    cout << "vector data: " << endl;  
    print_collection(v);  
  
    // pop_back() until it's empty, printing the last element as we go  
    while (v.begin() != v.end()) {   
        cout << "v.back(): "; print_elem(v.back()); cout << endl;  
        v.pop_back();  
    }  
}  
```  
  
##  <a name="a-namevectorrbegina-vectorrbegin"></a><a name="vector__rbegin"></a>  Vector::rbegin  
 Возвращает итератор, указывающий на первый элемент в обратном векторе.  
  
```  
reverse_iterator rbegin();

const_reverse_iterator rbegin() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Обратный итератор произвольного доступа, обращающийся к первому элементу в обратном векторе или адресации, что было последним элементом в необращенном вектор.  
  
### <a name="remarks"></a>Примечания  
 Если возвращаемое значение `rbegin` присвоено `const_reverse_iterator`, то объект вектора нельзя изменить. Если возвращаемое значение `rbegin` назначается `reverse_iterator`, то объект вектора можно изменить.  
  
### <a name="example"></a>Пример  
  
```  
// vector_rbegin.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::iterator v1_Iter;  
   vector <int>::reverse_iterator v1_rIter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
  
   v1_Iter = v1.begin( );  
   cout << "The first element of vector is "  
        << *v1_Iter << "." << endl;  
  
   v1_rIter = v1.rbegin( );  
   cout << "The first element of the reversed vector is "  
        << *v1_rIter << "." << endl;  
}  
```  
  
```Output  
The first element of vector is 1.  
The first element of the reversed vector is 2.  
```  
  
##  <a name="a-namevectorreferencea-vectorreference"></a><a name="vector__reference"></a>  Vector::Reference  
 Тип, предоставляющий ссылку на элемент, хранящийся в векторе.  
  
```  
typedef typename Allocator::reference reference;  
```  
  
### <a name="example"></a>Пример  
  В разделе [в](#vector__at) Пример использования **ссылки** в классе vector.  
  
##  <a name="a-namevectorrenda-vectorrend"></a><a name="vector__rend"></a>  Vector::rend  
 Возвращает итератор, адресующий расположение после последнего элемента в обратном векторе.  
  
```  
const_reverse_iterator rend() const;

reverse_iterator rend();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Обратный итератор произвольного доступа, который обращается к месту, следующему за последним элементом в обратном векторе (расположение перед первым элементом в необращенном вектора).  
  
### <a name="remarks"></a>Примечания  
 `rend` используется с обратным вектором как [окончания](#vector__end) используется с вектором.  
  
 Если возвращаемое значение `rend` назначается `const_reverse_iterator`, то объект вектора нельзя изменить. Если возвращаемое значение `rend` назначается `reverse_iterator`, то объект вектора можно изменить.  
  
 `rend` может использоваться, чтобы проверить, достиг ли Обратный итератор конца его вектор.  
  
 Значение, возвращаемое `rend`, не должно быть подвергнуто удалению ссылки.  
  
### <a name="example"></a>Пример  
  
```  
// vector_rend.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::reverse_iterator v1_rIter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
  
   for ( v1_rIter = v1.rbegin( ) ; v1_rIter != v1.rend( ) ; v1_rIter++ )  
      cout << *v1_rIter << endl;  
}  
```  
  
```Output  
2  
1  
```  
  
##  <a name="a-namevectorreservea-vectorreserve"></a><a name="vector__reserve"></a>  Vector::reserve  
 Резервирует минимальную длину хранилища для объекта вектора, при необходимости выделяя пространство.  
  
```  
void reserve(size_type count);
```  
  
### <a name="parameters"></a>Параметры  
 ` count`  
 Минимальная длина хранилища, выделяемого для вектора.  
  
### <a name="example"></a>Пример  
  
```  
// vector_reserve.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   //vector <int>::iterator Iter;  
  
   v1.push_back( 1 );  
   cout << "Current capacity of v1 = "   
      << v1.capacity( ) << endl;  
   v1.reserve( 20 );  
   cout << "Current capacity of v1 = "   
      << v1.capacity( ) << endl;  
}  
```  
  
```Output  
Current capacity of v1 = 1  
Current capacity of v1 = 20  
```  
  
##  <a name="a-namevectorresizea-vectorresize"></a><a name="vector__resize"></a>  Vector::Resize  
 Определяет новый размер вектора.  
  
```  
void resize(size_type Newsize);

void resize(size_type Newsize, Type Val);
```  
  
### <a name="parameters"></a>Параметры  
 `Newsize`  
 Новый размер вектора.  
  
 `Val`  
 Значение инициализации новых элементов, добавленных в вектор, если новый размер больше исходного. Если значение опущено, новые объекты используют конструктор по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Если размер контейнера меньше запрошенного размера, `Newsize`, элементы добавляются в вектор, пока он не достигнет требуемого размера. Если размер контейнера больше запрошенного, элементы, которые ближе всего к концу размера, удаляются, пока размер контейнера не станет равным `Newsize`. Если текущий размер контейнера совпадает с запрошенным, никакие действия не выполняются.  
  
 [размер](#vector__size) — это текущий размер вектора.  
  
### <a name="example"></a>Пример  
  
```cpp  
// vectorsizing.cpp  
// compile with: /EHsc /W4  
// Illustrates vector::reserve, vector::max_size,  
// vector::resize, vector::resize, and vector::capacity.  
//  
// Functions:  
//  
//    vector::max_size - Returns maximum number of elements vector could  
//                       hold.  
//  
//    vector::capacity - Returns number of elements for which memory has  
//                       been allocated.  
//  
//    vector::size - Returns number of elements in the vector.  
//  
//    vector::resize - Reallocates memory for vector, preserves its  
//                     contents if new size is larger than existing size.  
//  
//    vector::reserve - Allocates elements for vector to ensure a minimum  
//                      size, preserving its contents if the new size is  
//                      larger than existing size.  
//  
//    vector::push_back - Appends (inserts) an element to the end of a  
//                        vector, allocating memory for it if necessary.  
//  
//////////////////////////////////////////////////////////////////////  
  
// The debugger cannot handle symbols more than 255 characters long.  
// STL often creates symbols longer than that.  
// The warning can be disabled:  
//#pragma warning(disable:4786)  
  
#include <iostream>  
#include <vector>  
#include <string>  
  
using namespace std;  
  
template <typename C> void print(const string& s, const C& c) {  
    cout << s;  
  
    for (const auto& e : c) {  
        cout << e << " ";  
    }  
    cout << endl;  
}  
  
void printvstats(const vector<int>& v) {  
    cout << "   the vector's size is: " << v.size() << endl;  
    cout << "   the vector's capacity is: " << v.capacity() << endl;  
    cout << "   the vector's maximum size is: " << v.max_size() << endl;  
}  
  
int main()  
{  
    // declare a vector that begins with 0 elements.  
    vector<int> v;  
  
    // Show statistics about vector.  
    cout << endl << "After declaring an empty vector:" << endl;  
    printvstats(v);  
    print("   the vector's contents: ", v);  
  
    // Add one element to the end of the vector.  
    v.push_back(-1);  
    cout << endl << "After adding an element:" << endl;  
    printvstats(v);  
    print("   the vector's contents: ", v);  
  
    for (int i = 1; i < 10; ++i) {  
        v.push_back(i);  
    }  
    cout << endl << "After adding 10 elements:" << endl;  
    printvstats(v);  
    print("   the vector's contents: ", v);  
  
    v.resize(6);  
    cout << endl << "After resizing to 6 elements without an initialization value:" << endl;  
    printvstats(v);  
    print("   the vector's contents: ", v);  
  
    v.resize(9, 999);  
    cout << endl << "After resizing to 9 elements with an initialization value of 999:" << endl;  
    printvstats(v);  
    print("   the vector's contents: ", v);  
  
    v.resize(12);  
    cout << endl << "After resizing to 12 elements without an initialization value:" << endl;  
    printvstats(v);  
    print("   the vector's contents: ", v);  
  
    // Ensure there's room for at least 1000 elements.  
    v.reserve(1000);  
    cout << endl << "After vector::reserve(1000):" << endl;  
    printvstats(v);  
  
    // Ensure there's room for at least 2000 elements.  
    v.resize(2000);  
    cout << endl << "After vector::resize(2000):" << endl;  
    printvstats(v);  
}  
```  
  
##  <a name="a-namevectorreverseiteratora-vectorreverseiterator"></a><a name="vector__reverse_iterator"></a>  Vector::reverse_iterator  
 Тип, предоставляющий итератор произвольного доступа, который может читать или изменять любой элемент в обратном векторе.  
  
```  
typedef std::reverse_iterator<iterator> reverse_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип `reverse_iterator` используется для последовательного прохождения через вектор в обратную сторону.  
  
### <a name="example"></a>Пример  
  В примере показано [rbegin](#vector__rbegin).  
  
##  <a name="a-namevectorshrinktofita-vectorshrinktofit"></a><a name="vector__shrink_to_fit"></a>  Vector::shrink_to_fit  
 Удаляет лишнюю емкость.  
  
```  
void shrink_to_fit();
```  
  
### <a name="example"></a>Пример  
  
```  
// vector_shrink_to_fit.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   //vector <int>::iterator Iter;  
  
   v1.push_back( 1 );  
   cout << "Current capacity of v1 = "   
      << v1.capacity( ) << endl;  
   v1.reserve( 20 );  
   cout << "Current capacity of v1 = "   
      << v1.capacity( ) << endl;  
   v1.shrink_to_fit();  
   cout << "Current capacity of v1 = "   
      << v1.capacity( ) << endl;  
}  
```  
  
```Output  
Current capacity of v1 = 1  
Current capacity of v1 = 20  
Current capacity of v1 = 1  
```  
  
##  <a name="a-namevectorsizea-vectorsize"></a><a name="vector__size"></a>  Vector::size  
 Возвращает количество элементов в векторе.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущая длина вектора.  
  
### <a name="example"></a>Пример  
  
```  
// vector_size.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::size_type i;  
  
   v1.push_back( 1 );  
   i = v1.size( );  
   cout << "Vector length is " << i << "." << endl;  
  
   v1.push_back( 2 );  
   i = v1.size( );  
   cout << "Vector length is now " << i << "." << endl;  
}  
```  
  
```Output  
Vector length is 1.  
Vector length is now 2.  
```  
  
##  <a name="a-namevectorsizetypea-vectorsizetype"></a><a name="vector__size_type"></a>  Vector::size_type  
 Тип, считающий количество элементов в векторе.  
  
```  
typedef typename Allocator::size_type size_type;  
```  
  
### <a name="example"></a>Пример  
  В примере показано [мощности](#vector__capacity).  
  
##  <a name="a-namevectorswapa-vectorswap"></a><a name="vector__swap"></a>  Vector::Swap  
 Меняет местами элементы двух векторов.  
  
```  
void swap(
    vector<Type, Allocator>& right);

friend void swap(
    vector<Type, Allocator>& left,  
    vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
 Вектор, предоставляющий элементы для обмена местами, или вектор, элементы которого должны быть заменены на элементы вектора ` left`.  
  
 ` left`  
 Вектор, элементы которого должны поменяться местами с элементами вектора ` right`.  
  
### <a name="example"></a>Пример  
  
```  
// vector_swap.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1, v2;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
   v1.push_back( 3 );  
  
   v2.push_back( 10 );  
   v2.push_back( 20 );  
  
   cout << "The number of elements in v1 = " << v1.size( ) << endl;  
   cout << "The number of elements in v2 = " << v2.size( ) << endl;  
   cout << endl;  
  
   v1.swap( v2 );  
  
   cout << "The number of elements in v1 = " << v1.size( ) << endl;  
   cout << "The number of elements in v2 = " << v2.size( ) << endl;  
}  
```  
  
```Output  
The number of elements in v1 = 3  
The number of elements in v2 = 2  
  
The number of elements in v1 = 2  
The number of elements in v2 = 3  
```  
  
##  <a name="a-namevectorvaluetypea-vectorvaluetype"></a><a name="vector__value_type"></a>  Vector::value_type  
 Тип, представляющий тип данных, хранящихся в векторе.  
  
```  
typedef typename Allocator::value_type value_type;  
```  
  
### <a name="remarks"></a>Примечания  
 `value_type` является синонимом параметра шаблона **типа**.  
  
### <a name="example"></a>Пример  
  
```  
// vector_value_type.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector<int>::value_type AnInt;  
   AnInt = 44;  
   cout << AnInt << endl;  
}  
```  
  
```Output  
44  
```  
  
##  <a name="a-namevectorvectora-vectorvector"></a><a name="vector__vector"></a>  Vector::Vector  
 Создает вектор определенного размера, вектор с элементами определенного значения, вектор с определенным распределителем или вектор как копию какого-либо другого вектора или его части.  
  
```  
vector();

explicit vector(
    const Allocator& Al);

explicit vector(
    size_type Count);

vector(
    size_type Count,  
    const Type& Val);

vector(
    size_type Count,  
    const Type& Val,  
    const Allocator& Al);

vector(
    const vector& Right);

vector(
    vector&& Right);

vector(
    initializer_list<Type> IList,  
    const _Allocator& Al);

template <class InputIterator>  
vector(
 InputIterator First,  
    InputIterator Last);

template <class InputIterator>  
vector(
 InputIterator First,  
    InputIterator Last,  
    const Allocator& Al);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`Al`|Класс распределителя для использования с данным объектом. [get_allocator](#vector__get_allocator) возвращает класс распределителя для объекта.|  
|`Count`|Количество элементов в создаваемом векторе.|  
|`Val`|Значение элементов в создаваемом векторе.|  
|`Right`|Вектор, для которого создаваемый вектор станет копией.|  
|`First`|Положение первого элемента в диапазоне копируемых элементов.|  
|`Last`|Положение первого элемента за пределами диапазона копируемых элементов.|  
|`IList`|Объект initializer_list, содержащий elmeents для копирования.|  
  
### <a name="remarks"></a>Примечания  
 Все конструкторы хранят объект распределителя ( `Al`) и инициализируют вектор.  
  
 Первые два конструктора определяют пустой исходный вектор. Второй явно указывает тип распределителя ( `Al`) для использования.  
  
 Третий конструктор задает повторение указанного числа ( `Count`) элементов значения по умолчанию для класса `Type`.  
  
 Четвертый и пятый конструкторы указывают повтор ( `Count`) элементов со значением `Val`.  
  
 Шестой конструктор задает копию вектора `Right`.  
  
 Седьмой конструктор перемещает вектор `Right`.  
  
 Восьмой конструктор использует initializer_list, чтобы указать элементы.  
  
 Девятый и десятый конструкторы копируют диапазон [ `First`, `Last`) вектора.  
  
### <a name="example"></a>Пример  
  
```cpp  
// vector_ctor.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    vector <int>::iterator v1_Iter, v2_Iter, v3_Iter, v4_Iter, v5_Iter, v6_Iter;  
  
    // Create an empty vector v0  
    vector <int> v0;  
  
    // Create a vector v1 with 3 elements of default value 0  
    vector <int> v1(3);  
  
    // Create a vector v2 with 5 elements of value 2  
    vector <int> v2(5, 2);  
  
    // Create a vector v3 with 3 elements of value 1 and with the allocator   
    // of vector v2  
    vector <int> v3(3, 1, v2.get_allocator());  
  
    // Create a copy, vector v4, of vector v2  
    vector <int> v4(v2);  
  
    // Create a new temporary vector for demonstrating copying ranges  
    vector <int> v5(5);  
    for (auto i : v5) {  
        v5[i] = i;  
    }  
  
    // Create a vector v6 by copying the range v5[ first,  last)  
    vector <int> v6(v5.begin() + 1, v5.begin() + 3);  
  
    cout << "v1 =";  
    for (auto& v : v1){  
        cout << " " << v;  
    }  
    cout << endl;  
  
    cout << "v2 =";  
    for (auto& v : v2){  
        cout << " " << v;  
    }  
    cout << endl;  
  
    cout << "v3 =";  
    for (auto& v : v3){  
        cout << " " << v;  
    }  
    cout << endl;  
    cout << "v4 =";  
    for (auto& v : v4){  
        cout << " " << v;  
    }  
    cout << endl;  
  
    cout << "v5 =";  
    for (auto& v : v5){  
        cout << " " << v;  
    }  
    cout << endl;  
  
    cout << "v6 =";  
    for (auto& v : v6){  
        cout << " " << v;  
    }  
    cout << endl;  
  
    // Move vector v2 to vector v7  
    vector <int> v7(move(v2));  
    vector <int>::iterator v7_Iter;  
  
    cout << "v7 =";  
    for (auto& v : v7){  
        cout << " " << v;  
    }  
    cout << endl;  
  
    vector<int> v8{ { 1, 2, 3, 4 } };  
    for (auto& v : v8){  
        cout << " " << v ;  
    }  
    cout << endl;  
}  
  
```  
  
```Output  
v1 = 0 0 0v2 = 2 2 2 2 2v3 = 1 1 1v4 = 2 2 2 2 2v5 = 0 1 2 3 4v6 = 1 2v7 = 2 2 2 2 21 2 3 4  
```  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)

