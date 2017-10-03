---
title: "Класс allocator | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- memory/std::allocator
- memory/std::allocator::const_pointer
- memory/std::allocator::const_reference
- memory/std::allocator::difference_type
- memory/std::allocator::pointer
- memory/std::allocator::reference
- memory/std::allocator::size_type
- memory/std::allocator::value_type
- memory/std::allocator::address
- memory/std::allocator::allocate
- memory/std::allocator::construct
- memory/std::allocator::deallocate
- memory/std::allocator::destroy
- memory/std::allocator::max_size
- memory/std::allocator::rebind
dev_langs:
- C++
helpviewer_keywords:
- std::allocator [C++]
- std::allocator [C++], const_pointer
- std::allocator [C++], const_reference
- std::allocator [C++], difference_type
- std::allocator [C++], pointer
- std::allocator [C++], reference
- std::allocator [C++], size_type
- std::allocator [C++], value_type
- std::allocator [C++], address
- std::allocator [C++], allocate
- std::allocator [C++], construct
- std::allocator [C++], deallocate
- std::allocator [C++], destroy
- std::allocator [C++], max_size
- std::allocator [C++], rebind
ms.assetid: 3fd58076-56cc-43bb-ad58-b4b7c9c6b410
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 50967f59b594cfba30167b67dcb2802541a5eafc
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="allocator-class"></a>Класс allocator
Класс шаблона описывает объект, который управляет выделением и освобождением памяти для массивов объектов типа **Type**. Объект класса **allocator** является объектом распределителя по умолчанию, заданным в конструкторах для нескольких классов шаблонов контейнеров в стандартной библиотеке C++.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class Type>  
class allocator  
```  
  
#### <a name="parameters"></a>Параметры  
 *Тип*  
 Тип объекта, для которого выполняется выделение и освобождение памяти.  
  
## <a name="remarks"></a>Примечания  
 Все контейнеры библиотеки стандартов C++ имеют параметр шаблона, который по умолчанию имеет значение **allocator**. Создание контейнера с пользовательским распределителем дает возможность управлять выделением и освобождением памяти для элементов контейнера.  
  
 Например, объект распределителя может выделить память в закрытой куче или в общей памяти. Он также может выполнить оптимизацию для крупных или мелких объектов. Он может также указывать, посредством определения типов, которые он предоставляет, что доступ к элементам возможен только через специальные объекты метода доступа, управляющие общей памятью или выполняющие автоматическую сборку мусора. Таким образом, класс, который выделяет память с использованием объекта распределителя, должен использовать эти типы для объявления указателя и объектов ссылок, как это делают контейнеры в библиотеке стандартов C++.  
  
 **(Только C_++ 98/03)**При наследовании из класса allocator вы должны предоставить структуру [rebind](#rebind), у которой в определении типа `_Other` есть ссылки на созданный производный класс.  
  
 Таким образом, распределитель определяет следующие типы:  
  
- [pointer](#pointer) действует как указатель на **Type**.  
  
- [const_pointer](#const_pointer) действует как константный указатель на **Type**.  
  
- [reference](#reference) действует как ссылка на **Type**.  
  
- [const_reference](#const_reference) действует как константная ссылка на **Type**.  
  
 Эти типы**Type** определяют форму, какую должны принимать указатели и ссылки для выделенных элементов. ([allocator::pointer](#pointer) не обязательно совпадает с **Type**\* для всех объектов распределителя, даже если он содержит это очевидное определение для класса **allocator**.)  
  
 **C++11 and later:** чтобы включить операции перемещения в распределитель, используйте минимальный интерфейс распределителя и реализуйте конструктор копирования, операторы == и !=, функции allocate и deallocate. Дополнительные сведения и пример см. в статье [Распределители](../standard-library/allocators.md).  
  
## <a name="members"></a>Члены  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[allocator](#allocator)|Конструкторы, используемые для создания объектов `allocator`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[const_pointer](#const_pointer)|Тип, предоставляющий постоянный указатель на тип объекта, управляемого распределителем.|  
|[const_reference](#const_reference)|Тип, предоставляющий постоянную ссылку на тип объекта, управляемого распределителем.|  
|[difference_type](#difference_type)|Тип целого числа со знаком, который может представлять разницу между значениями указателей на тип объекта, управляемого распределителем.|  
|[pointer](#pointer)|Тип, предоставляющий указатель на тип объекта, управляемого распределителем.|  
|[reference](#reference)|Тип, предоставляющий ссылку на тип объекта, управляемого распределителем.|  
|[size_type](#size_type)|Тип целого числа без знака, который может представлять длину любой последовательности, которую объект класса шаблона `allocator` может выделить.|  
|[value_type](#value_type)|Тип, управляемый распределителем.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[address](#address)|Находит адрес объекта, значение которого задано.|  
|[allocate](#allocate)|Выделяет блок памяти, достаточный для хранения по крайней мере некоторого указанного числа элементов.|  
|[construct](#construct)|Создает определенный тип объекта по указанному адресу, инициализированный с использованием заданного значения.|  
|[deallocate](#deallocate)|Освобождает указанное число объектов из памяти, начиная с заданной позиции.|  
|[destroy](#destroy)|Вызывает деструктор объектов без освобождения памяти, в которой хранился объект.|  
|[max_size](#max_size)|Возвращает число элементов типа `Type`, которые могут быть выделены объектом класса `allocator` в пределах имеющейся свободной памяти.|  
|[rebind](#rebind)|Структура, позволяющая распределителю, предназначенному для объектов одного типа, выделять память для объектов другого типа.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор=](#op_eq)|Назначает один объект `allocator` другому объекту `allocator`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<memory>  
  
 **Пространство имен:** std  
  
##  <a name="address"></a>  allocator::address  
 Находит адрес объекта, значение которого задано.  
  
```  
pointer address(reference val) const;
const_pointer address(const_reference val) const;
```  
  
### <a name="parameters"></a>Параметры  
 `val`  
 Константное или неконстантное значение объекта, адрес которого ищется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Константный или неконстантный указатель на найденный объект соответственно константного или неконстантного значения.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает адрес `val` в форме, которую указатели должны принимать для выделенных элементов.  
  
### <a name="example"></a>Пример  
  
```cpp  
// allocator_address.cpp  
// compile with: /EHsc  
#include <memory>  
#include <algorithm>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 1 ; i <= 7 ; i++ )  
   {  
      v1.push_back( 2 * i );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   allocator<int>::const_pointer v1Ptr;  
   const int k = 8;  
   v1Ptr = v1Alloc.address( *find(v1.begin( ), v1.end( ), k) );  
   // v1Ptr = v1Alloc.address( k );  
   cout << "The integer addressed by v1Ptr has a value of: "  
        << "*v1Ptr = " << *v1Ptr << "." << endl;  
}  
```  
  
```Output  
The original vector v1 is:  
 ( 2 4 6 8 10 12 14 ).  
The integer addressed by v1Ptr has a value of: *v1Ptr = 8.  
```  
  
##  <a name="allocate"></a>  allocator::allocate  
 Выделяет блок памяти, достаточный для хранения по крайней мере некоторого указанного числа элементов.  
  
```  
pointer allocate(size_type count, const void* _Hint);
```  
  
### <a name="parameters"></a>Параметры  
 `count`  
 Количество элементов, для которых необходимо выделить достаточный объем памяти.  
  
 *_Hint*  
 Константный указатель, который может помочь объекту allocator удовлетворить запрос хранилища, найдя адрес объекта, выделенного до запроса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на выделенный объект или значение null, если память не была выделена.  
  
### <a name="remarks"></a>Примечания  
 Функция-член выделяет память для массива элементов count типа **Type** путем вызова оператора new( `count`). Она возвращает указатель на выделенный объект. Аргумент hint помогает некоторым распределителям улучшить расположение ссылок; недопустимый вариант — это адрес объекта, выделенный ранее тем же объектом allocator, который еще не был освобожден. Чтобы не предоставлять подсказок, используйте аргумент пустого указателя.  
  
### <a name="example"></a>Пример  
  
```cpp  
// allocator_allocate.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   allocator<int> v1Alloc;    
   allocator<int>::pointer v1aPtr;    
   v1aPtr = v1Alloc.allocate ( 10 );  
  
   int i;  
   for ( i = 0 ; i < 10 ; i++ )  
   {  
      v1aPtr[ i ] = i;  
   }  
  
   for ( i = 0 ; i < 10 ; i++ )  
   {  
      cout << v1aPtr[ i ] << " ";  
   }  
   cout << endl;    
   v1Alloc.deallocate( v1aPtr, 10 );  
}  
```  
  
```Output  
0 1 2 3 4 5 6 7 8 9   
```  
  
##  <a name="allocator"></a>  allocator::allocator  
 Конструкторы, используемые для создания объектов allocator.  
  
```  
allocator();
allocator(const allocator<Type>& right);
template <class Other>  
allocator(const allocator<Other>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Объект allocator для копирования.  
  
### <a name="remarks"></a>Примечания  
 Конструктор не выполняет никаких действий. Однако в целом объект allocator, построенный из другого объекта allocator, должен оцениваться как эквивалентный ему, и должно быть разрешено перемешивание выделения и освобождения объектов между этими двумя объектами allocator.  
  
### <a name="example"></a>Пример  
  
```cpp  
// allocator_allocator.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
class Int {  
public:  
   Int( int i )   
   {  
      cout << "Constructing " << ( void* )this  << endl;   
      x = i;  
      bIsConstructed = true;  
   };  
   ~Int( )   
   {  
      cout << "Destructing " << ( void* )this << endl;   
      bIsConstructed = false;  
   };  
   Int &operator++( )   
   {  
      x++;  
      return *this;  
   };  
   int x;  
private:  
   bool bIsConstructed;  
};  
  
int main( )   
{  
   allocator<double> Alloc;  
   vector <Int>:: allocator_type v1Alloc;  
  
   allocator<double> cAlloc(Alloc);   
   allocator<Int> cv1Alloc(v1Alloc);  
  
   if ( cv1Alloc == v1Alloc )  
      cout << "The allocator objects cv1Alloc & v1Alloc are equal."  
           << endl;  
   else  
      cout << "The allocator objects cv1Alloc & v1Alloc are not equal."  
           << endl;  
  
   if ( cAlloc == Alloc )  
      cout << "The allocator objects cAlloc & Alloc are equal."  
           << endl;  
   else  
      cout << "The allocator objects cAlloc & Alloc are not equal."  
           << endl;  
}  
```  
  
```Output  
The allocator objects cv1Alloc & v1Alloc are equal.  
The allocator objects cAlloc & Alloc are equal.  
```  
  
##  <a name="const_pointer"></a>  allocator::const_pointer  
 Тип, предоставляющий постоянный указатель на тип объекта, управляемого распределителем.  
  
```  
typedef const value_type *const_pointer;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип указателя описывает объект **ptr**, который с помощью выражения  **\*ptr** может обозначать любой константный объект, который может быть выделен объектом класса allocator шаблона.  
  
### <a name="example"></a>Пример  
  
```cpp  
// allocator_const_ptr.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 1 ; i <= 7 ; i++ )  
   {  
      v1.push_back( i * 2 );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   allocator<int>::const_pointer v1Ptr;  
   const int k = 10;  
   v1Ptr = v1Alloc.address( k );  
  
   cout << "The integer's address found has a value of: "  
        << *v1Ptr << "." << endl;  
}  
```  
  
```Output  
The original vector v1 is:  
 ( 2 4 6 8 10 12 14 ).  
The integer's address found has a value of: 10.  
```  
  
##  <a name="const_reference"></a>  allocator::const_reference  
 Тип, предоставляющий постоянную ссылку на тип объекта, управляемого распределителем.  
  
```  
typedef const value_type& const_reference;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот ссылочный тип описывает объект, который может обозначать любой константный объект, который может быть выделен объектом класса allocator шаблона.  
  
### <a name="example"></a>Пример  
  
```cpp  
// allocator_const_ref.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <double> v;  
   vector <double> ::iterator vIter, vfIter;  
   vector <double> :: allocator_type vAlloc;  
  
   int j;  
   for ( j = 1 ; j <= 7 ; j++ )  
   {  
      v.push_back( 100.0 * j );  
   }  
  
   cout << "The original vector v is:\n ( " ;  
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vfIter = v.begin( );  
   allocator<double>::const_reference vcref =*vfIter;  
   cout << "The value of the element referred to by vref is: "  
        << vcref << ",\n the first element in the vector." << endl;  
  
   // const references can have their elements modified,  
   // so the following would generate an error:  
   // vcref = 150;  
   // but the value of the first element could be modified through  
   // its nonconst iterator and the const reference would remain valid  
 *vfIter = 175;  
   cout << "The value of the element referred to by vcref,"  
        <<"\n after nofication through its nonconst iterator, is: "  
        << vcref << "." << endl;  
}  
```  
  
```Output  
The original vector v is:  
 ( 100 200 300 400 500 600 700 ).  
The value of the element referred to by vref is: 100,  
 the first element in the vector.  
The value of the element referred to by vcref,  
 after nofication through its nonconst iterator, is: 175.  
```  
  
##  <a name="construct"></a>  allocator::construct  
 Создает определенный тип объекта по указанному адресу, инициализированный с использованием заданного значения.  
  
```  
void construct(pointer ptr, const Type& val);
void construct(pointer ptr, Type&& val);
template <class _Other>  
void construct(pointer ptr, _Other&&...   val);
```  
  
### <a name="parameters"></a>Параметры  
 `ptr`  
 Указатель места, в котором должен создаваться объект.  
  
 `val`  
 Значение, с которым создаваемый объект будет инициализирован.  
  
### <a name="remarks"></a>Примечания  
 Первая функция-член — эквивалент **new** ( ( `void` \*) `ptr` ) **Type** ( `val` ).  
  
### <a name="example"></a>Пример  
  
```cpp  
// allocator_construct.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <algorithm>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 1 ; i <= 7 ; i++ )  
   {  
      v1.push_back( 3 * i );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   allocator<int>::pointer v1PtrA;  
   int kA = 6, kB = 7;  
   v1PtrA = v1Alloc.address( *find( v1.begin( ), v1.end( ), kA ) );  
   v1Alloc.destroy ( v1PtrA );  
   v1Alloc.construct ( v1PtrA , kB );  
  
   cout << "The modified vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The original vector v1 is:  
 ( 3 6 9 12 15 18 21 ).  
The modified vector v1 is:  
 ( 3 7 9 12 15 18 21 ).  
```  
  
##  <a name="deallocate"></a>  allocator::deallocate  
 Освобождает указанное число объектов из памяти, начиная с заданной позиции.  
  
```  
void deallocate(pointer ptr, size_type count);
```  
  
### <a name="parameters"></a>Параметры  
 `ptr`  
 Указатель на первый объект, который должен быть освобожден из хранилища.  
  
 `count`  
 Количество объектов для освобождения из хранилища.  
  
### <a name="remarks"></a>Примечания  
 Функция-член освобождает хранилище для массива, число объектов типа **тип** начиная `ptr`, путем вызова `operator delete(ptr)`. Указатель `ptr` должен быть возвращен ранее путем вызова [allocate](#allocate) для объекта allocator, который сравнивает его с  **\*this**, выделяя объект массива того же типа и размера. `deallocate` никогда не создает исключений.  
  
### <a name="example"></a>Пример  
  Пример использования этой функции-члена см. в разделе [allocator::allocate](#allocate).  
  
##  <a name="destroy"></a>  allocator::destroy  
 Вызывает деструктор объектов без освобождения памяти, в которой хранился объект.  
  
```  
void destroy(pointer ptr);
```  
  
### <a name="parameters"></a>Параметры  
 `ptr`  
 Указатель, обозначающий адрес уничтожаемого объекта.  
  
### <a name="remarks"></a>Примечания  
 Функция-член удаляет объект, назначенному с помощью `ptr`, путем вызова деструктора `ptr->` **тип**::**~ типа**.  
  
### <a name="example"></a>Пример  
  
```cpp  
// allocator_destroy.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <algorithm>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 1 ; i <= 7 ; i++ )  
   {  
      v1.push_back( 2 * i );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   allocator<int>::pointer v1PtrA;  
   int kA = 12, kB = -99;  
   v1PtrA = v1Alloc.address( *find(v1.begin( ), v1.end( ), kA) );  
   v1Alloc.destroy ( v1PtrA );  
   v1Alloc.construct ( v1PtrA , kB );  
  
   cout << "The modified vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The original vector v1 is:  
 ( 2 4 6 8 10 12 14 ).  
The modified vector v1 is:  
 ( 2 4 6 8 10 -99 14 ).  
```  
  
##  <a name="difference_type"></a>  allocator::difference_type  
 Тип целого числа со знаком, который может представлять разницу между значениями указателей на тип объекта, управляемого распределителем.  
  
```  
typedef ptrdiff_t difference_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип целого числа со знаком описывает объект, который может представлять разницу между адресами любых двух элементов в последовательности, которые может выделить объект класса allocator шаблона.  
  
### <a name="example"></a>Пример  
  
```cpp  
// allocator_diff_type.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 0 ; i <= 7 ; i++ )  
   {  
      v1.push_back( i * 2 );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   allocator<int>::const_pointer v1PtrA, v1PtrB;  
   const int kA = 4, kB =12;  
   v1PtrA = v1Alloc.address( kA );  
   v1PtrB = v1Alloc.address( kB );  
   allocator<int>::difference_type v1diff = *v1PtrB - *v1PtrA;  
  
   cout << "Pointer v1PtrA addresses " << *v1PtrA << "." << endl;  
   cout << "Pointer v1PtrB addresses " << *v1PtrB <<  "." << endl;  
   cout << "The difference between the integer's addresses is: "  
        << v1diff << "." << endl;  
}  
```  
  
```Output  
The original vector v1 is:  
 ( 0 2 4 6 8 10 12 14 ).  
Pointer v1PtrA addresses 4.  
Pointer v1PtrB addresses 12.  
The difference between the integer's addresses is: 8.  
```  
  
##  <a name="max_size"></a> allocator::max_size  
 Возвращает количество элементов типа **Type**, которые могут быть выделены объектом класса allocator в пределах имеющейся свободной памяти.  
  
```  
size_type max_size() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество элементов, которые могут быть выделены.  
  
### <a name="example"></a>Пример  
  
```cpp  
// allocator_max_size.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 1 ; i <= 7 ; i++ )  
   {  
      v1.push_back( i );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   vector <double> v2;  
   vector <double> ::iterator v2Iter;  
   vector <double> :: allocator_type v2Alloc;  
   allocator<int>::size_type v1size;  
   v1size = v1Alloc.max_size( );  
  
   cout << "The number of integers that can be allocated before\n"  
        << " the free memory in the vector v1 is used up is: "  
        << v1size << "." << endl;  
  
   int ii;  
   for ( ii = 1 ; ii <= 7 ; ii++ )  
   {  
      v2.push_back( ii * 10.0 );  
   }  
  
   cout << "The original vector v2 is:\n ( " ;  
   for ( v2Iter = v2.begin( ) ; v2Iter != v2.end( ) ; v2Iter++ )  
      cout << *v2Iter << " ";  
   cout << ")." << endl;  
   allocator<double>::size_type v2size;  
   v2size = v2Alloc.max_size( );  
  
   cout << "The number of doubles that can be allocated before\n"  
        << " the free memory in the vector v2 is used up is: "  
        << v2size << "." << endl;  
}  
```  
  
##  <a name="op_eq"></a>  allocator::operator=  
 Назначает один объект allocator другому объекту allocator.  
  
```  
template <class Other>  
allocator<Type>& operator=(const allocator<Other>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Объект allocator для назначения другому такому объекту.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на объект allocator  
  
### <a name="remarks"></a>Примечания  
 Оператор присваивания шаблона не выполняет никаких действий. Однако в целом объект allocator, назначенный другому объекту allocator, должен оцениваться как эквивалентный ему, и должно быть разрешено перемешивание выделения и освобождения объектов между этими двумя объектами allocator.  
  
### <a name="example"></a>Пример  
  
```cpp  
// allocator_op_assign.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
class Int {  
public:  
   Int(int i)   
   {  
      cout << "Constructing " << ( void* )this  << endl;   
      x = i;  
      bIsConstructed = true;  
   };  
   ~Int( ) {  
      cout << "Destructing " << ( void* )this << endl;   
      bIsConstructed = false;  
   };  
   Int &operator++( )   
   {  
      x++;  
      return *this;  
   };  
   int x;  
private:  
   bool bIsConstructed;  
};  
  
int main( )   
{  
   allocator<Int> Alloc;  
   allocator<Int> cAlloc ;  
   cAlloc = Alloc;      
}  
```  
  
##  <a name="pointer"></a>  allocator::pointer  
 Тип, предоставляющий указатель на тип объекта, управляемого распределителем.  
  
```  
typedef value_type *pointer;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип указателя описывает объект **ptr**, который с помощью выражения  **\*ptr** может обозначать любой объект, который может быть выделен объектом класса allocator шаблона.  
  
### <a name="example"></a>Пример  
  
```cpp  
// allocator_ptr.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 1 ; i <= 7 ; i++ )  
   {  
      v1.push_back( 3 * i );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   allocator<int>::const_pointer v1Ptr;  
   const int k = 12;  
   v1Ptr = v1Alloc.address( k );  
  
   cout << "The integer addressed by v1Ptr has a value of: "  
        << "*v1Ptr = " << *v1Ptr << "." << endl;     
}  
```  
  
```Output  
The original vector v1 is:  
 ( 3 6 9 12 15 18 21 ).  
The integer addressed by v1Ptr has a value of: *v1Ptr = 12.  
```  
  
##  <a name="rebind"></a>  allocator::rebind  
 Структура, позволяющая распределителю, предназначенному для объектов одного типа, выделять память для объектов другого типа.  
```  
struct rebind {    typedef allocator<_Other> other ;    };  
```  
### <a name="parameters"></a>Параметры  
 *other*  
 Тип элемента, для которого выделяется память.  
  
### <a name="remarks"></a>Примечания  
 Эту структуру удобно использовать для выделения памяти для типа, который отличается от типа элемента реализуемого контейнера.  
  
 Класс шаблона элемента определяет другой тип. Его единственная цель — предоставить имя типа **allocator**\<_ **Other**>, если имеется имя типа **allocator**\< **Type**>.  
  
 Например, если имеется объект allocator **al** типа **A**, можно выделить объект типа **_Other** с помощью выражения:  
  
```  
A::rebind<Other>::other(al).allocate(1, (Other *)0)  
```  
  
 Кроме того, можно дать имя его типу указателя, написав тип:  
  
```  
A::rebind<Other>::other::pointer  
```  
  
### <a name="example"></a>Пример  
  
```cpp  
// allocator_rebind.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <algorithm>  
#include <vector>  
  
using namespace std;  
  
typedef vector<int>::allocator_type IntAlloc;  
int main( )   
{  
   IntAlloc v1Iter;  
   vector<int> v1;  
  
   IntAlloc::rebind<char>::other::pointer pszC =  
      IntAlloc::rebind<char>::other(v1.get_allocator()).allocate(1, (void *)0);  
  
   int * pInt = v1Iter.allocate(10);  
}  
```  
  
##  <a name="reference"></a>  allocator::reference  
 Тип, предоставляющий ссылку на тип объекта, управляемого распределителем.  
  
```  
typedef value_type& reference;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот ссылочный тип описывает объект, который может обозначать любой объект, который может быть выделен объектом класса allocator шаблона.  
  
### <a name="example"></a>Пример  
  
```cpp  
// allocator_reference.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <double> v;  
   vector <double> ::iterator vIter, vfIter;  
   vector <double> :: allocator_type vAlloc;  
  
   int j;  
   for ( j = 1 ; j <= 7 ; j++ )  
   {  
      v.push_back( 100.0 * j );  
   }  
  
   cout << "The original vector v is:\n ( " ;  
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vfIter = v.begin( );  
   allocator<double>::reference vref =*vfIter;  
   cout << "The value of the element referred to by vref is: "  
        << vref << ",\n the first element in the vector." << endl;  
  
   // nonconst references can have their elements modified  
   vref = 150;  
   cout << "The element referred to by vref after being modified is: "  
        << vref << "." << endl;  
}  
```  
  
```Output  
The original vector v is:  
 ( 100 200 300 400 500 600 700 ).  
The value of the element referred to by vref is: 100,  
 the first element in the vector.  
The element referred to by vref after being modified is: 150.  
```  
  
##  <a name="size_type"></a>  allocator::size_type  
 Тип целого числа без знака, который может представлять длину любой последовательности, которую объект класса allocator шаблона может выделить.  
  
```  
typedef size_t size_type;  
```  
  
### <a name="example"></a>Пример  
  
```cpp  
// allocator_size_type.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )  
{  
   vector <double> v;  
   vector <double> ::iterator vIter;  
   vector <double> :: allocator_type vAlloc;  
  
   int j;  
   for ( j = 1 ; j <= 7 ; j++ )  
   {  
      v.push_back( 100.0 * j );  
   }  
  
   cout << "The original vector v is:\n ( " ;  
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   allocator<double>::size_type vsize;  
   vsize = vAlloc.max_size( );  
  
   cout << "The number of doubles that can be allocated before\n"  
        << " the free memory in the vector v is used up is: "  
        << vsize << "." << endl;  
}  
```  
  
##  <a name="value_type"></a>  allocator::value_type  
 Тип, управляемый распределителем.  
  
```  
typedef Type value_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом для параметра-шаблона **Type**.  
  
### <a name="example"></a>Пример  
  
```cpp  
// allocator_value_type.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
using namespace std;  
  
int main( )   
{  
   vector <double> v;  
   vector <double> ::iterator vIter, vfIter;  
   vector <double> :: allocator_type vAlloc;  
  
   int j;  
   for ( j = 1 ; j <= 7 ; j++ )  
   {  
      v.push_back( 100.0 * j );  
   }  
  
   cout << "The original vector v is:\n ( " ;  
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vfIter = v.begin( );  
   allocator<double>::value_type vecVal = 150.0;  
 *vfIter = vecVal;  
   cout << "The value of the element addressed by vfIter is: "  
        << *vfIter << ",\n the first element in the vector." << endl;  
  
   cout << "The modified vector v is:\n ( " ;  
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The original vector v is:  
 ( 100 200 300 400 500 600 700 ).  
The value of the element addressed by vfIter is: 150,  
 the first element in the vector.  
The modified vector v is:  
 ( 150 200 300 400 500 600 700 ).  
```  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)


