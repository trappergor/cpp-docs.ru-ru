---
title: decltype (C++)
ms.date: 11/04/2016
f1_keywords:
- decltype_cpp
helpviewer_keywords:
- operators [C++], decltype
- decltype operator
- operators [C++], type of an expression
- operators [C++], deduce expression type
ms.assetid: 6dcf8888-8196-4f13-af50-51e3797255d4
ms.openlocfilehash: 0a4e9eb015df056dfe2a35da18cfa50875ced432
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222454"
---
# <a name="decltype--c"></a>decltype (C++)


Описатель типа **decltype** возвращает тип заданного выражения. Описатель типа **decltype** вместе с [ключевым словом auto](../cpp/auto-cpp.md) используются главным образом разработчиками, которые создают библиотеки шаблонов. Используйте **auto** и **decltype** для объявления функции-шаблона, тип возвращаемого значения которой зависит от типов ее шаблонных аргументов. Вы также можете использовать **auto** и **decltype** для объявления функции-шаблона, которая является оболочкой для вызова другой функции и возвращает тип возвращаемого значения последней.


## <a name="syntax"></a>Синтаксис

```
decltype( expression )
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|

|*expression*|Выражение. Дополнительные сведения см. в разделе [Выражения](../cpp/expressions-cpp.md).|

## <a name="return-value"></a>Возвращаемое значение

Тип параметра *expression*.

## <a name="remarks"></a>Примечания

Cпецификатор типа **decltype** поддерживается в Visual Studio 2010 или более поздних версиях и может использоваться с машинным или управляемым кодом. `decltype(auto)` (C++ 14) поддерживается в Visual Studio 2015 и более поздних версиях.

Компилятор использует следующие правила для определения типа параметра *expression*.

– Если параметр *expression* — это идентификатор или [доступ к члену класса](../cpp/member-access-operators-dot-and.md), `decltype(expression)` — это тип сущности с именем *expression*. Если такая сущность отсутствует или параметр *expression* является именем набора перегруженных функций, компилятор выдает сообщение об ошибке.

– Если параметр *expression* представляет собой вызов обычной функции или функции перегруженного оператора, `decltype(expression)` является возвращаемым типом функции. Скобки вокруг перегруженного оператора игнорируются.

– Если параметр *expression* представляет собой [rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md), `decltype(expression)` — это тип *expression*. Если параметр *expresion* представляет собой [lvalue](../cpp/lvalues-and-rvalues-visual-cpp.md), `decltype(expression)` — это [ссылка lvalue](../cpp/lvalue-reference-declarator-amp.md) на тип *expression*.

В следующем примере кода показано несколько способов использования описателя типа **decltype**. Для начала допустим, что вы написали следующий код.


```cpp
int var;
const int&& fx();
struct A { double x; }
const A* a = new A();
```


Далее, рассмотрим типы, возвращаемые четырьмя инструкциями **decltype**, приведенные в следующей таблице.


|Оператор|Тип|Примечания|
|---------------|----------|-----------|
|`decltype(fx());`|`const int&&`|[Ссылка rvalue](../cpp/rvalue-reference-declarator-amp-amp.md) на константное **целое**.|
|`decltype(var);`|**int**|Тип переменной `var`.|

|`decltype(a->x);`|**double**|Тип доступа к члену.|
|`decltype((a->x));`|`const double&`|Внутренние скобки вызывают вычисление оператора в качестве выражения, а не доступа к члену. И поскольку `a` объявляется как указатель `const`, тип является ссылкой на **const double**.|

## <a name="decltype-and-auto"></a>Decltype и Auto

В C++ 14 можно использовать `decltype(auto)` без завершающего типа возвращаемого значения для объявления функции-шаблона, тип возвращаемого значения которой зависит от типов ее шаблонных аргументов.

В C++ 11 можно использовать описатель типа **decltype** для завершающего возвращаемого типа вместе с ключевым словом **Auto** , чтобы объявить функцию-шаблон, тип возвращаемого значения которого зависит от типов его аргументов шаблона. Например, рассмотрим следующий пример кода, в котором тип возвращаемого значения функции шаблона зависит от типов аргументов шаблона. Рассмотрим это в следующем примере кода, где заполнитель *UNKNOWN* показывает, что указать тип возвращаемого значения невозможно.


```cpp
template<typename T, typename U>
UNKNOWN func(T&& t, U&& u){ return t + u; };
```


Введение спецификатора типа **decltype** позволяет разработчику получить тип выражения, которое возвращает функция-шаблон. Используйте *альтернативный синтаксис объявления функций*, приведенный ниже, ключевое слово **auto** и описатель **decltype** для объявления *поздно задаваемого* типа возвращаемого значения. Поздно задаваемый возвращаемый тип определяется во время компиляции объявления, а не во время разработки.

Следующий прототип иллюстрирует синтаксис альтернативного объявления функции. Обратите внимание, что квалификаторы **const** и **volatile**, а также [спецификация исключений](../cpp/exception-specifications-throw-cpp.md) **throw** являются необязательными. Заполнитель *function_body* представляет составную инструкцию, которая определяет действия функции. При написании кода рекомендуется, чтобы заполнитель *expression* в инструкции **decltype** соответствовал выражению, заданному инструкцией **return** в *function_body*, если таковая имеется.

**auto** *function_name* **(** *parameters*<sub>opt</sub> **)** **const**<sub>opt</sub> **volatile**<sub>opt</sub> **->** **decltype (** *expression* **)** **throw**<sub>opt</sub> **{** *function_body* **};**

В следующем примере кода поздно задаваемый тип возвращаемого значения функции-шаблона `myFunc` определяется типами шаблонных аргументов `t` и `u`. Согласно принятым стандартам программирования в примере кода также используются ссылки rvalue и шаблон функции `forward`, которая поддерживает *точную пересылку*. Дополнительные сведения см. в статье [Декларатор ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).


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

Функции пересылки представляют собой оболочки для вызова других функций. Представьте себе шаблон функции, которая пересылает свои аргументы (или результаты выражения с этими аргументами) другой функции. Кроме того, функция пересылки возвращает результат вызова другой функции. В этом сценарии тип возвращаемого значения функции пересылки должен совпадать с типом возвращаемого значения функции, для которой функция пересылки является оболочкой.


В этом случае записать подходящее выражение типа без описателя типа **decltype** невозможно. Спецификатор типа **decltype** позволяет использовать универсальные функции пересылки, так как он не теряет необходимой информации о том, возвращает ли функция ссылочный тип. Пример кода функции пересылки см. в предыдущем примере функции-шаблона `myFunc`.

## <a name="example"></a>Пример

В следующем примере кода объявляется поздно задаваемый тип возвращаемого значения функции-шаблона `Plus()`. Функция `Plus` обрабатывает два своих операнда с использованием перегрузки **operator+**. Следовательно, интерпретация оператора сложения (+) и тип возвращаемого значения функции `Plus` зависят от типов аргументов функции.


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


**Visual Studio 2017 и более поздние версии.** Компилятор анализирует аргументы decltype при объявлении шаблона, а не при создании его экземпляра. Соответственно, независимая специализация, обнаруженная в аргументе decltype, не откладывается до момента создания экземпляра, а обрабатывается сразу. Кроме того, в это время выявляются все возникающие ошибки.	


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

Visual Studio 2010 или более поздние версии.


`decltype(auto)` требует Visual Studio 2015 или более поздней версии.

