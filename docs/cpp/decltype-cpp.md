---
title: "decltype (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- decltype_cpp
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], decltype
- decltype operator
- operators [C++], type of an expression
- operators [C++], deduce expression type
ms.assetid: 6dcf8888-8196-4f13-af50-51e3797255d4
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 1f07590275ca6e2b65d6f3d58bcea825acc71f73
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="decltype--c"></a>decltype (C++)
Описатель типа `decltype` предоставляет тип заданного выражения. `decltype` Описатель типа вместе с [ключевое слово auto](../cpp/auto-cpp.md), используется главным образом для разработчиков, которые создают библиотеки шаблонов. Используйте `auto` и `decltype` для объявления функции шаблонов, возвращаемый тип которой зависит от типов аргументов его шаблонов. Либо используйте `auto` и `decltype` для объявления функции шаблона, которая создает программу-оболочку для вызова другой функции, а затем возвращает возвращаемый тип функции с программой-оболочкой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
decltype( expression )  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`expression`|Выражения. Дополнительные сведения см. в разделе [выражений](../cpp/expressions-cpp.md).|  
  
## <a name="return-value"></a>Возвращаемое значение  
 Тип параметра `expression`.  
  
## <a name="remarks"></a>Примечания  
 Описатель типа `decltype` поддерживается в Visual C++ 2010 или более поздних версиях и может использоваться с машинным или управляемым кодом. `decltype(auto)` (C++ 14) поддерживается в Visual Studio 2015 и более поздних версиях.  
  
 Компилятор использует следующие правила для определения типа параметра `expression`.  
  
-   Если `expression` параметр — идентификатор или [доступ к члену класса](../cpp/member-access-operators-dot-and.md), `decltype(expression)` — это тип сущности, с именем `expression`. Если такая сущность отсутствует или параметр `expression` именует набор перегруженных функций, компилятор создает сообщение об ошибке.  
  
-   Если `expression` параметр представляет собой вызов функции или перегруженной функцией оператора, `decltype(expression)` имеет тип возвращаемого значения функции. Скобки вокруг перегруженного оператора игнорируются.  
  
-   Если `expression` параметр [rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md), `decltype(expression)` тип `expression`. Если `expression` параметр [lvalue](../cpp/lvalues-and-rvalues-visual-cpp.md), `decltype(expression)` — [ссылки lvalue](../cpp/lvalue-reference-declarator-amp.md) типу `expression`.  
  
 В следующем примере кода продемонстрированы некоторые варианты использования описателя типов `decltype`. Допустим, во-первых, что были закодированы следующие операторы.  
  
```cpp  
int var;  
const int&& fx();   
struct A { double x; }  
const A* a = new A();  
```  
  
 Затем изучите типы, возвращаемые четырьмя операторами `decltype`, в таблице ниже.  
  
|Оператор|Тип|Примечания|  
|---------------|----------|-----------|  
|`decltype(fx());`|`const int&&`|[Ссылка rvalue](../cpp/rvalue-reference-declarator-amp-amp.md) для `const int`.|  
|`decltype(var);`|`int`|Тип переменной `var`.|  
|`decltype(a->x);`|`double`|Тип членского доступа.|  
|`decltype((a->x));`|`const double&`|Внутренние скобки вызывают оценку оператора в качестве выражения, а не членского доступа. А поскольку `a` объявляется как указатель `const`, тип является ссылкой на `const double`.|  
  
## <a name="decltype-and-auto"></a>Decltype и Auto  
 В C ++ 14 можно использовать `decltype(auto)` без завершающего возвращаемого типа для объявления функции шаблона, возвращаемый тип которой зависит от типов его аргументов шаблона.  
  
 В C++ 11 можно использовать описатель типа `decltype` для завершающего возвращаемого типа вместе с ключевым словом `auto`, чтобы объявить функцию-шаблон, возвращаемый тип которой зависит от типов его аргументов шаблона. Например, рассмотрим следующий пример кода, в котором тип возвращаемого значения функции шаблона зависит от типов аргументов шаблона. В примере кода *Неизвестный* указывает заполнитель, не может быть указан тип возвращаемого значения.  
  
```cpp  
template<typename T, typename U>  
UNKNOWN func(T&& t, U&& u){ return t + u; };   
```  
  
 Внедрение описателя типа `decltype` позволяет разработчику получить тип выражения, возвращаемого функцией шаблона. Используйте *альтернативный синтаксис объявления функций* см. ниже, `auto` ключевое слово и `decltype` описатель для объявления типа *поздно заданный* тип возвращаемого значения. Поздно заданный тип возвращаемого значения определяется, когда происходит компиляция, а не кодирование объявления.  
  
 Следующий прототип иллюстрирует синтаксис альтернативного объявления функции. Обратите внимание, что `const` и `volatile` квалификаторы и `throw` [спецификацией исключений](../cpp/exception-specifications-throw-cpp.md) являются необязательными. *Тело_функции* заполнитель представляет составную инструкцию, которая указывает, что делает функция. Как с рекомендацией *выражение* заполнителя в `decltype` оператор должен соответствовать выражению, заданному `return` инструкции, если таковая имеется, в *тело_функции*.  
  
 **Auto** *function_name* **(** *параметры*<sub>необ</sub> **)** ** const**<sub>необ</sub> **volatile**<sub>необ</sub> ** -> ** **decltype (** *выражение* **)** **throw**<sub>необ</sub> **{** *тело_функции* **};**  
  
 В следующем примере кода поздно заданный возвращаемый тип функции шаблона `myFunc` определяется типами аргументов шаблона `t` и `u`. Как с рекомендацией, в примере кода также используются ссылки rvalue и `forward` функции шаблона, который поддерживает *точную пересылку*. Дополнительные сведения см. в статье [Декларатор ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
```cpp  
//C++11  
 template<typename T, typename U>  
auto myFunc(T&& t, U&& u) -> decltype (forward<T>(t) + forward<U>(u))   
        { return forward<T>(t) + forward<U>(u); };  
  
//C++14  
template<typename T, typename U>  
decltype(auto) myFunc(T&& t, U&& u)   
        { return forward<T>(t) + forward<U>(u); };  
  
```  
  
## <a name="decltype-and-forwarding-functions-c11"></a>Decltype и функции пересылки (C++ 11)  
 Функции пересылки создают программы-оболочек для вызовов других функций. Рассмотрим шаблон функции, который пересылает свои аргументы (или результаты выражения с этими аргументами) другой функции. Кроме того, функция пересылки возвращает результат вызова другой функции. В этом сценарии возвращаемый тип функции пересылки должен совпадать с возвращаемым типом функции в программе-оболочке.  
  
 В этом сценарии невозможно создать подобающее выражение типа без описателя типа `decltype`. Описатель типа `decltype` включает универсальные функции пересылки, поскольку не теряет необходимой информации о том, возвращает ли функция ссылочный тип. Пример кода функции пересылки см. в предыдущем примере шаблонной функции `myFunc`.  
  
## <a name="example"></a>Пример  
 В следующем примере кода объявляется поздно заданный возвращаемый тип шаблонной функции `Plus()`. Функция `Plus` обрабатывает два свои операнда с перегрузкой `operator+`. Следовательно, интерпретация добавочного оператора (+) и возвращаемый тип функции `Plus` зависят от типов аргументов функции.  
  
```cpp  
// decltype_1.cpp  
// compile with: cl /EHsc decltype_1.cpp  
  
#include <iostream>  
#include <string>  
#include <utility>  
#include <iomanip>  
  
using namespace std;  
  
template<typename T1, typename T2>  
auto Plus(T1&& t1, T2&& t2) ->   
   decltype(forward<T1>(t1) + forward<T2>(t2))  
{  
   return forward<T1>(t1) + forward<T2>(t2);  
}  
  
class X  
{  
   friend X operator+(const X& x1, const X& x2)  
   {  
      return X(x1.m_data + x2.m_data);  
   }  
  
public:  
   X(int data) : m_data(data) {}  
   int Dump() const { return m_data;}  
private:  
   int m_data;  
};  
  
int main()  
{  
   // Integer   
   int i = 4;  
   cout <<   
      "Plus(i, 9) = " <<   
      Plus(i, 9) << endl;  
  
   // Floating point  
   float dx = 4.0;  
   float dy = 9.5;  
   cout <<     
      setprecision(3) <<   
      "Plus(dx, dy) = " <<  
      Plus(dx, dy) << endl;  
  
   // String        
   string hello = "Hello, ";  
   string world = "world!";  
   cout << Plus(hello, world) << endl;  
  
   // Custom type  
   X x1(20);  
   X x2(22);  
   X x3 = Plus(x1, x2);  
   cout <<   
      "x3.Dump() = " <<   
      x3.Dump() << endl;  
}  
```  
  
```Output  
Plus(i, 9) = 13
Plus(dx, dy) = 13.5
Hello, world!
x3.Dump() = 42
```
  
## <a name="example"></a>Пример
**Visual Studio 2017 и более поздних версий:** компилятор анализирует decltype аргументы при объявленные шаблоны, а не создан. Соответственно, независимая специализация, обнаруженная в аргументе decltype, не откладывается до момента создания и немедленно обрабатывается. Кроме того, в это время выявляются все возникающие ошибки.

В следующем примере показана такая ошибка компилятора, возникающая во время объявления.

```cpp
#include <utility>
template <class T, class ReturnT, class... ArgsT> class IsCallable
{
public:
   struct BadType {};
   template <class U>
   static decltype(std::declval<T>()(std::declval<ArgsT>()...)) Test(int); //C2064. Should be declval<U>
   template <class U>
   static BadType Test(...);
   static constexpr bool value = std::is_convertible<decltype(Test<T>(0)), ReturnT>::value;
};

constexpr bool test1 = IsCallable<int(), int>::value;
static_assert(test1, "PASS1");
constexpr bool test2 = !IsCallable<int*, int>::value;
static_assert(test2, "PASS2");
```

## <a name="requirements"></a>Требования  
 Visual C++ 2010 и выше.  
  
 `decltype(auto)`требуется Visual Studio 2015 или более поздней версии.  
  

