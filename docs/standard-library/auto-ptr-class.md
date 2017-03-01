---
title: "Класс auto_ptr | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::auto_ptr
- std.auto_ptr
- auto_ptr
- memory/std::auto_ptr
dev_langs:
- C++
helpviewer_keywords:
- auto_ptr class
ms.assetid: 7f9108b6-9eb3-4634-b615-cf7aa814f23b
caps.latest.revision: 26
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 92da9cbca9d7594bcb740d70fb57ce453d769e17
ms.lasthandoff: 02/24/2017

---
# <a name="autoptr-class"></a>Класс auto_ptr
Заключает в оболочку интеллектуальный указатель вокруг ресурса, что гарантирует, что ресурс будет удален автоматически, когда точка управления выходит за пределы блока.  
  
 Более мощный класс `unique_ptr` имеет более высокий приоритет, чем `auto_ptr`. Дополнительные сведения см. в разделе [Класс unique_ptr](../standard-library/unique-ptr-class.md).  
  
 Дополнительные сведения о `throw()` и об обработке исключений см. в статье [Спецификации исключений](../cpp/exception-specifications-throw-cpp.md).  
  
## <a name="syntax"></a>Синтаксис  
 ```   
class auto_ptr {
public:
    typedef Type element_type;
    explicit auto_ptr(Type* ptr = 0) throw();
    auto_ptr(auto_ptr<Type>& right) throw()
        ;
    template <class Other>
    operator auto_ptr<Other>() throw();
    template <class Other>
    auto_ptr<Type>& operator=(auto_ptr<Other>& right) throw();
    template <class Other>
    auto_ptr(auto_ptr<Other>& right);
    auto_ptr<Type>& operator=(auto_ptr<Type>& right);
    ~auto_ptr();
    Type& operator*() const throw();
    Type * operator->()const throw();
    Type *get() const throw();
    Type *release()throw();
    void reset(Type* ptr = 0);
};
```  
#### <a name="parameters"></a>Параметры  
 ` right`  
 `auto_ptr`, из которого необходимо получить существующий ресурс.  
  
 ` ptr`  
 Указатель, указанный для замены сохраненного указателя.  
  
## <a name="remarks"></a>Примечания  
 Этот класс шаблона описывает интеллектуальный указатель, который называется `auto_ptr,`, на выделенный объект. Указатель должен быть пустым или должен обозначать объект, выделенный `new`. `auto_ptr` передает право владения, если сохраненное значение присваивается другому объекту (сохраненное значение заменяется после перемещения с пустым указателем). Деструктор `auto_ptr<Type>` удаляет выделенный объект. `auto_ptr<Type>` гарантирует, что выделенный объект автоматически удаляется при выходе точки управления за пределы блока даже с использованием созданного исключения. Не следует создавать два объекта `auto_ptr<Type>`, владеющих одним объектом.  
  
 Вы можете передать объект `auto_ptr<Type>` по значению в виде аргумента в вызове функции. `auto_ptr` не может быть элементом любого контейнера стандартной библиотеки. Вы не можете надежно управлять последовательностью объектов `auto_ptr<Type>` с помощью контейнера стандартной библиотеки C++.  
  
## <a name="members"></a>Члены  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[auto_ptr](#auto_ptr__auto_ptr)|Конструктор для объектов типа `auto_ptr`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[element_type](#auto_ptr__element_type)|Этот тип является синонимом для параметра шаблона `Type`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[get](#auto_ptr__get)|Эта функция-член возвращает сохраненный указатель `myptr`.|  
|[release](#auto_ptr__release)|Этот член заменяет сохраненный указатель `myptr` на пустой указатель и возвращает сохраненный ранее указатель.|  
|[reset](#auto_ptr__reset)|Эта функция-член вычисляет выражение `deleteÂ myptr`, но только если значение сохраненного указателя `myptr` изменяется после вызова функции. Затем она заменяет сохраненный указатель на `ptr`.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор=](#auto_ptr__operator_eq)|Оператор присваивания, который передает право владения от одного объекта `auto_ptr` другому.|  
|[оператор*](#auto_ptr__operator_star)|Оператор удаления ссылки для объектов типа `auto_ptr`.|  
|[оператор>](#auto_ptr__operator-_gt_)|Оператор для разрешения доступа к членам.|  
|[оператор auto_ptr\<Other>](#auto_ptr__operator_auto_ptr_lt_other_gt_)|Приводит из одного вида `auto_ptr` в другой вид `auto_ptr`.|  
|[оператор auto_ptr_ref\<Other>](#auto_ptr__operator_auto_ptr_ref_lt_other_gt_)|Приводит из `auto_ptr` в `auto_ptr_ref`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<memory>  
  
 **Пространство имен:** std  
  
##  <a name="a-nameautoptrautoptra--autoptrautoptr"></a><a name="auto_ptr__auto_ptr"></a>  auto_ptr::auto_ptr  
 Конструктор для объектов типа `auto_ptr`.  
  
```   
explicit auto_ptr(Type* ptr  = 0) throw();

auto_ptr(auto_ptr<Type>& right) throw();

auto_ptr(auto _ptr_ref<Type> right) throw();

template <class Other>  
auto _ptr(auto _ptr<Other>& right) throw();
```  
  
### <a name="parameters"></a>Параметры  
 ` ptr`  
 Указатель на объект, который инкапсулирует `auto_ptr`.  
  
 ` right`  
 Объект `auto_ptr` для копирования конструктором.  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор сохраняет ` ptr` в **myptr**, сохраненном указателе на выделенный объект. Второй конструктор передает право владения указателем, сохраненным в ` right`, сохраняя ` right`. [release](#auto_ptr__release) в **myptr**.  
  
 Третий конструктор действует так же, как второй, за исключением того, что он сохраняет **right**. `ref`. **release** в **myptr**, где `ref` — ссылка, хранящаяся в ` right`.  
  
 Конструктор шаблона работает так же, как второй конструктор, при условии, что указатель на **Other** можно неявно преобразовать в указатель на **Type**.  
  
### <a name="example"></a>Пример  
  
```cpp  
// auto_ptr_auto_ptr.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
class Int   
{  
public:  
   Int(int i)   
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
  
void function ( auto_ptr<Int> &pi )  
{  
   ++( *pi );  
   auto_ptr<Int> pi2( pi );  
   ++( *pi2 );  
   pi = pi2;  
}  
  
int main( )   
{  
   auto_ptr<Int> pi ( new Int( 5 ) );  
   cout << pi->x << endl;  
   function( pi );  
   cout << pi->x << endl;  
}  
```  
  
```Output  
Constructing 00311AF8  
5  
7  
Destructing 00311AF8  
```  
  
##  <a name="a-nameautoptrelementtypea--autoptrelementtype"></a><a name="auto_ptr__element_type"></a>  auto_ptr::element_type  
 Этот тип является синонимом для параметра-шаблона **Type**.  
  
```  
 
typedef Type element  _type;  
```  
  
##  <a name="a-nameautoptrgeta--autoptrget"></a><a name="auto_ptr__get"></a>  auto_ptr::get  
 Эта функция-член возвращает сохраненный указатель **myptr**.  
  
```   
Type *get() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Сохраненный указатель **myptr**.  
  
### <a name="example"></a>Пример  
  
```cpp  
// auto_ptr_get.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
using namespace std;  
  
class Int   
{  
public:  
   Int(int i)   
   {  
      x = i;  
      cout << "Constructing " << ( void* )this  << " Value: " << x << endl;   
   };  
   ~Int( )   
   {  
      cout << "Destructing " << ( void* )this << " Value: " << x << endl;   
   };  
  
   int x;  
  
};  
  
int main( )   
{  
   auto_ptr<Int> pi ( new Int( 5 ) );  
   pi.reset( new Int( 6 ) );  
   Int* pi2 = pi.get ( );  
   Int* pi3 = pi.release ( );  
   if (pi2 == pi3)  
      cout << "pi2 == pi3" << endl;  
   delete pi3;  
}  
```  
  
```Output  
Constructing 00311AF8 Value: 5  
Constructing 00311B88 Value: 6  
Destructing 00311AF8 Value: 5  
pi2 == pi3  
Destructing 00311B88 Value: 6  
```  
  
##  <a name="a-nameautoptroperatoreqa--autoptroperator"></a><a name="auto_ptr__operator_eq"></a>  auto_ptr::operator=  
 Оператор присваивания, который передает право владения от одного объекта `auto_ptr` другому.  
  
```  
template <class Other>  
auto_ptr<Type>& operator=(auto_ptr<Other>& right) throw();
auto_ptr<Type>& operator=(auto_ptr<Type>& right) throw();
auto_ptr<Type>& operator=(auto_ptr_ref<Type> right) throw();
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
 Объект типа `auto_ptr`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на объект типа `auto_ptr`\< **Type**>.  
  
### <a name="remarks"></a>Примечания  
 Это присваивание вычисляет выражение **delete myptr**, но только если сохраненный указатель **myptr** изменяется в результате присваивания. Затем оно передает право владения указателем, сохраненным в_ *Right*, сохраняя \_ *Right*. [release](#auto_ptr__release) в **myptr**. Функция возвращает **\*this**.  
  
### <a name="example"></a>Пример  
  Пример использования этого оператора-члена см. в разделе [auto_ptr::auto_ptr](#auto_ptr__auto_ptr).  
  
##  <a name="a-nameautoptroperatorstara--autoptroperator"></a><a name="auto_ptr__operator_star"></a>  auto_ptr::operator*  
 Оператор удаления ссылки для объектов типа `auto_ptr`.  
  
```   
Type& operator*() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на объект типа **Type** , которому принадлежит указатель.  
  
### <a name="remarks"></a>Примечания  
 Оператор косвенного обращения возвращает `*`[get](#auto_ptr__get). Следовательно, сохраненный указатель не должен быть пустым.  
  
### <a name="example"></a>Пример  
  Пример использования функции-члена см. в разделе [auto_ptr::auto_ptr](#auto_ptr__auto_ptr).  
  
##  <a name="a-nameautoptroperator-gta--autoptroperator-gt"></a><a name="auto_ptr__operator-_gt_"></a>  auto_ptr::operator-&gt;  
 Оператор для разрешения доступа к членам.  
  
```   
Type * operator->() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Член объекта, которому принадлежит **auto_ptr**.  
  
### <a name="remarks"></a>Примечания  
 Оператор выбора возвращает [get](#auto_ptr__get)`( )`, поэтому выражение *ap*-> **member** ведет себя так же, как ( *ap*. **get**( ) )-> **member**, где *ap* — это объект класса `auto_ptr`\< **Type**>. Таким образом, сохраненный указатель не должен быть пустым, и **Type** должен быть классом, структурой или типом объединения с членом **member**.  
  
### <a name="example"></a>Пример  
  Пример использования функции-члена см. в разделе [auto_ptr::auto_ptr](#auto_ptr__auto_ptr).  
  
##  <a name="a-nameautoptroperatorautoptrltothergta--autoptroperator-autoptrltothergt"></a><a name="auto_ptr__operator_auto_ptr_lt_other_gt_"></a>  auto_ptr::operator auto_ptr&lt;Other&gt;  
 Приводит из одного вида `auto_ptr` в другой вид `auto_ptr`.  
  
```   
template <class Other>  
operator auto _ptr<Other>() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Оператор приведения типов возвращает `auto_ptr` \< **Other**>( **\*this**).  
  
### <a name="example"></a>Пример  
  
```cpp  
// auto_ptr_op_auto_ptr.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
int main()  
{  
   auto_ptr<int> pi ( new int( 5 ) );  
   auto_ptr<const int> pc = ( auto_ptr<const int> )pi;  
}  
```  
  
##  <a name="a-nameautoptroperatorautoptrrefltothergta--autoptroperator-autoptrrefltothergt"></a><a name="auto_ptr__operator_auto_ptr_ref_lt_other_gt_"></a>  auto_ptr::operator auto_ptr_ref&lt;Other&gt;  
 Выполняет приведение из `auto_ptr` в **auto_ptr_ref**.  
  
```   
template <class Other>  
operator auto _ptr  _ref<Other>() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Оператор приведения типов возвращает **auto_ptr_ref**\< **Other**>( **\*this**).  
  
### <a name="example"></a>Пример  
  
```cpp  
// auto_ptr_op_auto_ptr_ref.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
class C {
public:
    C(int _i) : m_i(_i) {
    }
    ~C() {
        cout << "~C:  " << m_i << "\n";
    }
    C &operator =(const int &x) {
        m_i = x;
        return *this;
    }
    int m_i;
};
void f(auto_ptr<C> arg) {
};
int main()
{
    const auto_ptr<C> ciap(new C(1));
    auto_ptr<C> iap(new C(2));

    // Error: this implies transfer of ownership of iap's pointer  
    // f(ciap);   
    f(iap); // compiles, but gives up ownership of pointer  

            // here, iap owns a destroyed pointer so the following is bad:  
            // *iap = 5; // BOOM  

    cout << "main exiting\n";
}
```  
  
```Output  
~C:  2  
main exiting  
~C:  1  
```  
  
##  <a name="a-nameautoptrreleasea--autoptrrelease"></a><a name="auto_ptr__release"></a>  auto_ptr::release  
 Этот член заменяет сохраненный указатель **myptr** пустым указателем и возвращает ранее хранившийся там указатель.  
  
```   
Type *release() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ранее сохраненный указатель.  
  
### <a name="remarks"></a>Примечания  
 Этот член заменяет сохраненный указатель **myptr** пустым указателем и возвращает ранее хранившийся там указатель.  
  
### <a name="example"></a>Пример  
  
```cpp  
// auto_ptr_release.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
using namespace std;  
  
class Int
{
public:
    Int(int i)
    {
        x = i;
        cout << "Constructing " << (void*)this << " Value: " << x << endl;
    };
    ~Int() {
        cout << "Destructing " << (void*)this << " Value: " << x << endl;
    };

    int x;

};

int main()
{
    auto_ptr<Int> pi(new Int(5));
    pi.reset(new Int(6));
    Int* pi2 = pi.get();
    Int* pi3 = pi.release();
    if (pi2 == pi3)
        cout << "pi2 == pi3" << endl;
    delete pi3;
}
```  
  
```Output  
Constructing 00311AF8 Value: 5  
Constructing 00311B88 Value: 6  
Destructing 00311AF8 Value: 5  
pi2 == pi3  
Destructing 00311B88 Value: 6  
```  
  
##  <a name="a-nameautoptrreseta--autoptrreset"></a><a name="auto_ptr__reset"></a>  auto_ptr::reset  
 Эта функция-член вычисляет выражение **delete**Â **myptr**, но только если значение сохраненного указателя **myptr** изменяется в результате вызова функции. Затем она заменяет сохраненный указатель на **ptr**.  
  
```   
void reset(Type* ptr = 0);
```  
  
### <a name="parameters"></a>Параметры  
 ` ptr`  
 Указатель, заданный для замены сохраненного указателя **myptr**.  
  
### <a name="example"></a>Пример  
  
```cpp  
// auto_ptr_reset.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;

class Int
{
public:
    Int(int i)
    {
        x = i;
        cout << "Constructing " << (void*)this << " Value: " << x << endl;
    };
    ~Int()
    {
        cout << "Destructing " << (void*)this << " Value: " << x << endl;
    };

    int x;
};

int main()
{
    auto_ptr<Int> pi(new Int(5));
    pi.reset(new Int(6));
    Int* pi2 = pi.get();
    Int* pi3 = pi.release();
    if (pi2 == pi3)
        cout << "pi2 == pi3" << endl;
    delete pi3;
}
```  
  
```Output  
Constructing 00311AF8 Value: 5  
Constructing 00311B88 Value: 6  
Destructing 00311AF8 Value: 5  
pi2 == pi3  
Destructing 00311B88 Value: 6  
```  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Класс unique_ptr](../standard-library/unique-ptr-class.md)


